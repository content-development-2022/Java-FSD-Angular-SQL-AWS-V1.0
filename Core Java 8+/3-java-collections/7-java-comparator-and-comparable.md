# Comparator and Comparable in Java

**Content**

[1. Introduction](#1-introduction)

[2. Setting Up the Example](#2-setting-up-the-example)

[3. Comparable](#3-comparable)

[4. Comparator](#4-comparator)

[4.1. Creating Comparators](#41-creating-comparators)

[4.2. Comparators in Action](#42-comparators-in-action)

[4.3. Java 8 Comparators](#43-java-8-comparators)

[5. Comparator vs Comparable](#5-comparator-vs-comparable)

[6. Avoiding the Subtraction Trick](#6-avoiding-the-subtraction-trick)

[7. Reference](#7-reference)

# 1. Introduction

-   Comparisons in Java are quite easy, until they're not.
-   When working with custom types, or trying to compare objects that aren't directly comparable, we need to make use of a comparison strategy.
-   We can build one simply by making use of the *Comparator* or *Comparable* interfaces.

# 2. Setting Up the Example

-   Let's use an example of a football team, where we want to line up the players by their rankings.
-   We'll start by creating a simple *Player* class:

```java
public class Player {
    private int ranking;
    private String name;
    private int age;
    // constructor, getters, setters
}
```

-   Next, we'll create a *PlayerSorter* class to create our collection, and attempt to sort it using *Collections.sort*:

```java
public class PlayerSorter {
    public static void main(String[] args) {
        List<Player> footballTeam = new ArrayList<>();
        Player player1 = new Player(59, "John", 20);
        Player player2 = new Player(67, "Roger", 22);
        Player player3 = new Player(45, "Steven", 24);
        footballTeam.add(player1);
        footballTeam.add(player2);
        footballTeam.add(player3);
        System.out.println("Before Sorting : " + footballTeam);
        Collections.sort(footballTeam);
        System.out.println("After Sorting : " + footballTeam);
    }
}
```

-   As expected, this results in a compile-time error:

```
The method sort(List<T>) in the type Collections is not applicable for the arguments (ArrayList<Player>)
```

-   Now let's try to understand what we did wrong here.

# 3. Comparable

-   As the name suggests, **Comparable is an interface defining a strategy of comparing an object with other objects of the same type. This is called the class's “natural ordering.”**
-   In order to be able to sort, we must define our *Player* object as comparable by implementing the *Comparable* interface:

```java
public class Player implements Comparable<Player> {
    // same as before
    @Override
    public int compareTo(Player otherPlayer) {
        return Integer.compare(getRanking(), otherPlayer.getRanking());
    }
}
```

-   **The sorting order is decided by the return value of the compareTo()** **method.**
-   The *Integer.compare(x, y)* returns -1 if *x* is less than *y*, 0 if they're equal, and 1 otherwise.
-   The method returns a number indicating whether the object being compared is less than, equal to, or greater than the object being passed as an argument.
-   Now when we run our *PlayerSorter*, we can see our *Players* sorted by their ranking:

```
Before Sorting : [John, Roger, Steven]
After Sorting : [Steven, John, Roger]
```

-   Now that we have a clear understanding of natural ordering with *Comparable*, let's see **how we can use other types of ordering in a more flexible manner** than by directly implementing an interface.

# 4. Comparator

-   **The Comparator interface defines a compare(arg1, arg2) method** with two arguments that represent compared objects, and works similarly to the *Comparable.compareTo()* method.

## 4.1. Creating *Comparators*

-   To create a *Comparator,* we have to implement the *Comparator* interface.
-   For our first example, we'll create a *Comparator* to use the *ranking* attribute of *Player* to sort the players:

```java
public class PlayerRankingComparator implements Comparator<Player> {
    @Override
    public int compare(Player firstPlayer, Player secondPlayer) {
        return Integer.compare(firstPlayer.getRanking(), secondPlayer.getRanking());
    }
}
```

-   Similarly, we can create a *Comparator* to use the *age* attribute of *Player* to sort the players:

```java
public class PlayerAgeComparator implements Comparator<Player> {
    @Override
    public int compare(Player firstPlayer, Player secondPlayer) {
        return Integer.compare(firstPlayer.getAge(), secondPlayer.getAge());
    }
}
```

## 4.2. *Comparators* in Action

-   To demonstrate the concept, let's modify our *PlayerSorter* by introducing a second argument to the *Collections.sort* method, which is actually the instance of *Comparator* we want to use.

**Using this approach, we can override the natural ordering**:

```java
PlayerRankingComparator playerComparator = new PlayerRankingComparator();
Collections.sort(footballTeam, playerComparator);
```

-   Now let's run our *PlayerRankingSorter to* see the result:

```
Before Sorting : [John, Roger, Steven]
After Sorting by ranking : [Steven, John, Roger]
```

-   If we want a different sorting order, we only need to change the *Comparator* we're using:

```java
PlayerAgeComparator playerComparator = new PlayerAgeComparator();
Collections.sort(footballTeam, playerComparator);
```

-   Now when we run our *PlayerAgeSorter*, we can see a different sort order by *age:*

```
Before Sorting : [John, Roger, Steven]
After Sorting by age : [Roger, John, Steven]
```

## 4.3. Java 8 *Comparators*

-   Java 8 provides new ways of defining *Comparators* by using lambda expressions, and the *comparing()* static factory method.
-   Let's see a quick example of how to use a lambda expression to create a *Comparator*:

```java
Comparator byRanking = (Player player1, Player player2) -> Integer.compare(player1.getRanking(), player2.getRanking());
```

-   The *Comparator.comparing* method takes a method calculating the property that will be used for comparing items, and returns a matching *Comparator* instance:

```java
Comparator<Player> byRanking = Comparator . comparing(Player::getRanking);
Comparator<Player> byAge = Comparator. comparing(Player::getAge);
```

# 5. Comparator vs Comparable

-   **The Comparable interface is a good choice to use for defining the default ordering,** or in other words, if it's the main way of comparing objects.

**So why use a Comparator if we already have Comparable?**

There are several reasons why:

-   Sometimes we can't modify the source code of the class whose objects we want to sort, thus making the use of *Comparable* impossible
-   Using *Comparators* allows us to avoid adding additional code to our domain classes
-   We can define multiple different comparison strategies, which isn't possible when using *Comparable*

# 6. Avoiding the Subtraction Trick

-   In this document, we've used the *Integer.compare()* method to compare two integers. However, one might argue that we should use this clever one-liner instead:

```java
Comparator<Player> comparator = (p1, p2) -> p1.getRanking() - p2.getRanking();
```

-   **Although it's much more concise than other solutions, it can be a victim of integer overflows in Java**:

```java
Player player1 = new Player(59, "John", Integer.MAX_VALUE);
Player player2 = new Player(67, "Roger", -1);
List<Player> players = Arrays.asList(player1, player2);
players.sort(comparator);
```

-   Since -1 is much less than the *Integer.MAX_VALUE*, “Roger” should come before “John” in the sorted collection.
-   **However, due to integer overflow, the “Integer.MAX_VALUE – (-1)” will be less than zero**.
-   So based on the *Comparator/Comparable* contract, the *Integer.MAX_VALUE* is less than -1, which is obviously incorrect.
-   Therefore, despite what we expected, “John” comes before “Roger” in the sorted collection:

```java
assertEquals("John", players.get(0).getName());
assertEquals("Roger", players.get(1).getName());
```

# 7. Reference

1.  https://www.baeldung.com/java-comparator-comparable
