# Set

**Content**

1\. Set

1.1 HashSet

1.2 LinkedHashSet

1.3 TreeSet

2\. References

## 1. Set

-   A Set is a Collection that cannot contain duplicate elements.
-   There are three main implementations of Set interface:
1.  HashSet
2.  TreeSet
3.  LinkedHashSet.

## 1.1 HashSet

-   HashSet which stores its elements in a hash table, is the best-performing implementation.
-   HashSet allows only unique elements.
-   It doesn’t maintain the insertion order which means element inserted last can appear at first when traversing the HashSet.

**Example:**

```java
import java.util.*;
public class JavaExample{
  public static void main(String args[]){
    HashSet<String> set =  new HashSet<>();
    set.add("Paul");
    set.add("Ram");
    set.add("Aaron");
    set.add("Leo");
    set.add("Becky");

    Iterator<String> it = set.iterator();
    while(it.hasNext()){
      System.out.println(it.next());
    }
  }
}
```

**Output:**

```
Aaron
Leo
Paul
Ram
Becky
```

## 1.2 LinkedHashSet

-   Unlike HashSet, the LinkedHashSet maintains insertion order.

**Example:**

```java
import java.util.*;
public class JavaExample{
  public static void main(String args[]){
    LinkedHashSet<String> set = new LinkedHashSet<>();
    set.add("Paul");
    set.add("Ram");
    set.add("Aaron");
    set.add("Leo");
    set.add("Becky");

    Iterator<String> it = set.iterator();
    while(it.hasNext()){
      System.out.println(it.next());
    }
  }
}
```

**Output:**

```
Paul
Ram
Aaron
Leo
Becky
```

## 1.3 TreeSet

-   TreeSet stores elements in a red-black tree. It is substantially slower than HashSet.
-   TreeSet class implements SortedSet interface, which allows TreeSet to order its elements based on their values, which means TreeSet elements are sorted in ascending order.

**Example:**

```java
import java.util.*;
public class JavaExample{
  public static void main(String args[]){
    TreeSet<String> set = new TreeSet<>();
    set.add("Paul");
    set.add("Ram");
    set.add("Aaron");
    set.add("Leo");
    set.add("Becky");

    Iterator<String> it = set.iterator();
    while(it.hasNext()){
      System.out.println(it.next());
    }
  }
}
```

**Output:**

```
Aaron
Becky
Leo
Paul
Ram
```

## 2. References

1.  https://beginnersbook.com/java-collections-tutorials/
