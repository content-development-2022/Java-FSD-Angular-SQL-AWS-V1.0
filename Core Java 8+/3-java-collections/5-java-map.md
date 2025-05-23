# Map

**Content**

[1. Map](#1-map)

[1.1 HashMap](#11-hashmap)

[1.2 TreeMap](#12-treemap)

[1.3 LinkedHashMap](#13-linkedhashmap)

[2. References](#2-references)

## 1. Map

-   A Map is an object that maps keys to values.
-   **Keys** are unique values associated with individual **Values**.
-   A map cannot contain duplicate keys.
-   Each key is associated with a single value.

    ![Maps in Java - Java Map Interface - Edureka](media/map.png)

-   We can access and modify values using the keys associated with them.

**Note:** The Map interface maintains 3 different sets:

1.  the set of keys
2.  the set of values
3.  the set of key/value associations (mapping).
-   There are three main implementations of Map interfaces:
1.  HashMap
2.  TreeMap
3.  LinkedHashMap.

## 1.1 HashMap

-   Java HashMap allows null key and null values.
-   HashMap is not an ordered collection.
-   You can iterate over HashMap entries through keys set but they are not guaranteed to be in the order of their addition to the HashMap.
-   HashMap is almost similar to Hashtable except that it’s unsynchronized and allows null key and values.
-   HashMap uses it’s inner class Node\<K,V\> for storing map entries.
-   HashMap stores entries into multiple singly linked lists, called buckets or bins.
-   Default number of bins is 16 and it’s always power of 2.
-   HashMap uses hashCode() and equals() methods on keys for get and put operations.
-   So HashMap key object should provide good implementation of these methods.
-   This is the reason immutable classes are better suitable for keys, for example String and Interger.
-   Java HashMap is not thread safe, for multithreaded environment you should use ConcurrentHashMap class or get synchronized map using Collections.synchronizedMap() method.

**How HashMap works internally in Java?**

## ![D:\\content-development-2022\\Revature-Next-Gen-Java-AWS-Angular-Extended-v3.1\\Core Java 8+\\3-java-collections\\media\\hashmap.png](media/hashmap.png)

## 1.1.1 Add Items

-   The HashMap class has many useful methods. For example, to add items to it, use the put() method:

**Example**

```java
// Import the HashMap class
import java.util.HashMap;

public class Main {
  public static void main(String[] args) {
    // Create a HashMap object called capitalCities
    HashMap<String, String> capitalCities = new HashMap<String, String>();

    // Add keys and values (Country, City)
    capitalCities.put("England", "London");
    capitalCities.put("Germany", "Berlin");
    capitalCities.put("Norway", "Oslo");
    capitalCities.put("USA", "Washington DC");
    System.out.println(capitalCities);
  }
}
```

**Output:**

```
{USA=Washington DC, Norway=Oslo, England=London, Germany=Berlin}
```

## 1.1.2 Access an Item

-   To access a value in the HashMap, use the get() method and refer to its key:

**Example:**

```java
capitalCities.get("England");
```

## 1.1.3 Remove an Item

-   To remove an item, use the remove() method and refer to the key:

**Example:**

```java
import java.util.HashMap;

public class Main {
  public static void main(String[] args) {
    HashMap<String, String> capitalCities = new HashMap<String, String>();
    capitalCities.put("England", "London");
    capitalCities.put("Germany", "Berlin");
    capitalCities.put("Norway", "Oslo");
    capitalCities.put("USA", "Washington DC");
    capitalCities.remove("England");
    System.out.println(capitalCities); 
  }
}
```

**Output:**

```
{USA=Washington DC, Norway=Oslo, Germany=Berlin}
```

-   To remove all items, use the clear() method:

**Example**

```java
capitalCities.clear();
```

## 1.1.4 HashMap Size

-   To find out how many items there are, use the size() method:

**Example**

```java
capitalCities.size();
```

## 1.1.5 Loop Through a HashMap

-   Loop through the items of a HashMap with a **for-each** loop.

**Note:** Use the keySet() method if you only want the keys, and use the values() method if you only want the values:

**Example-1**: **Print only keys using for each loop**

```java
import java.util.HashMap;

public class Main {
  public static void main(String[] args) {
    HashMap<String, String> capitalCities = new HashMap<String, String>();
    capitalCities.put("England", "London");
    capitalCities.put("Germany", "Berlin");
    capitalCities.put("Norway", "Oslo");
    capitalCities.put("USA", "Washington DC");
    
    for (String i : capitalCities.keySet()) {
      System.out.println(i);
    }
  }
}
```

**Output:**

```
USA
Norway
England
Germany
```

**Example-2: Print only values** **using for each loop**

```java
import java.util.HashMap;

public class Main {
  public static void main(String[] args) {
    HashMap<String, String> capitalCities = new HashMap<String, String>();
    capitalCities.put("England", "London");
    capitalCities.put("Germany", "Berlin");
    capitalCities.put("Norway", "Oslo");
    capitalCities.put("USA", "Washington DC");
    
    for (String i : capitalCities.values()) {
      System.out.println(i);
    }
  }
}
```

**Ouput:**

```
Washington DC
Oslo
London
Berlin
```

**Example-3: Print keys and values using for each loop**

```java
for (String i : capitalCities.keySet()) {
  System.out.println("key: " + i + " value: " + capitalCities.get(i));
}
```

-   You can also loop through an HashMap with **Iterator** :

**Example-4:**

```java
import java.util.*;
public class JavaExample{
  public static void main(String args[]){
    HashMap<Integer, String> hmap = new HashMap<>();

    //key and value pairs
    hmap.put(101, "Chaitanya");
    hmap.put(105, "Derick");
    hmap.put(111, "Logan");
    hmap.put(120, "Paul");

    //print HashMap elements
    Set set = hmap.entrySet();
    Iterator iterator = set.iterator();
    while(iterator.hasNext()) {
      Map.Entry m = (Map.Entry)iterator.next();
      System.out.print("key is: "+ m.getKey() + " & Value is: ");
      System.out.println(m.getValue());
    }
  }
}
```

**Output:**

```
Key is: 101 & value is: Chaitanya
Key is: 120 & value is: Paul
Key is: 105 & value is: Derick
Key is: 111 & value is: Logan
```

## 1.2 TreeMap

**Some of the major characteristics of TreeMap in Java are as follows:**

-   The TreeMap class that implements treemap in Java is a part of java.util package. It implements the Map interface.
-   The TreeMap class extends AbstractMap class and also implements the NavigableMap and SortedMap (indirectly) interface.
-   TreeMap is not synchronized.
-   By default, TreeMap elements are in ascending order.
-   TreeMap does not allow duplicate elements.
-   TreeMap allows null values but not null keys.
-   It is substantially slower than HashMap.

**The below diagram shows the class hierarchy for the TreeMap class.**

![class hierarchy](media/treemap-hierarchy.png)

**How TreeMap works internally in Java?**

![How TreeMap Works Internally in Java - Javatpoint](media/treemap.png)

## 1.2.1 Creating a TreeMap

-   In order to create a TreeMap, we must import the java.util.TreeMap package first.
-   Once we import the package, here is how we can create a TreeMap in Java.

```java
TreeMap<Key, Value> numbers = new TreeMap<>();
```

-   In the above code, we have created a TreeMap named *numbers* without any arguments.
-   In this case, the elements in TreeMap are sorted naturally (ascending order).
-   However, we can customize the sorting of elements by using the Comparator interface.

Here,

-   *Key* - a unique identifier used to associate each element (value) in a map
-   *Value* - elements associated by keys in a map

## 1.2.2 Insert Elements to TreeMap

-   put() - inserts the specified key/value mapping (entry) to the map
-   putAll() - inserts all the entries from specified map to this map
-   putIfAbsent() - inserts the specified key/value mapping to the map if the specified key is not present in the map

**Example:**

```java
import java.util.TreeMap;
class Main {
  public static void main(String[] args) {
      // Creating TreeMap of even numbers
      TreeMap<String, Integer> evenNumbers = new TreeMap<>();
      // Using put()
      evenNumbers.put("Two", 2);
      evenNumbers.put("Four", 4);
      // Using putIfAbsent()
      evenNumbers.putIfAbsent("Six", 6);
      System.out.println("TreeMap of even numbers: " + evenNumbers);
     //Creating TreeMap of numbers
     TreeMap<String, Integer> numbers = new TreeMap<>();
     numbers.put("One", 1);
     // Using putAll()
     numbers.putAll(evenNumbers);
     System.out.println("TreeMap of numbers: " + numbers);
   }
}
```

**Output**

```
TreeMap of even numbers: {Four=4, Six=6, Two=2}
TreeMap of numbers: {Four=4, One=1, Six=6, Two=2}
```

## 1.2.3 Access TreeMap Elements

-   entrySet() - returns a set of all the key/values mapping (entry) of a treemap.
-   keySet() - returns a set of all the keys of a tree map.
-   values() - returns a set of all the maps of a tree map.

**Example:**

```java
import java.util.TreeMap;
class Main {
  public static void main(String[] args) {
    TreeMap<String, Integer> numbers = new TreeMap<>();
    numbers.put("One", 1);
    numbers.put("Two", 2);
    numbers.put("Three", 3);
    System.out.println("TreeMap: " + numbers);
    // Using entrySet()
    System.out.println("Key/Value mappings: " +     numbers.entrySet());
    // Using keySet()
    System.out.println("Keys: " + numbers.keySet());
    // Using values()
    System.out.println("Values: " + numbers.values());
  }
}
```

**Output**

```
TreeMap: {One=1, Three=3, Two=2}
Key/Value mappings: [One=1, Three=3, Two=2]
Keys: [One, Three, Two]
Values: [1, 3, 2]
```

## 1.2.4 Remove TeeMap Elements

-   remove(key) - returns and removes the entry associated with the specified key from a TreeMap
-   remove(key, value) - removes the entry from the map only if the specified key is associated with the specified value and returns a boolean value

**Example:**

```java
import java.util.TreeMap;
class Main {
  public static void main(String[] args) {
    TreeMap<String, Integer> numbers = new TreeMap<>();
    numbers.put("One", 1);
    numbers.put("Two", 2);
    numbers.put("Three", 3);
    System.out.println("TreeMap: " + numbers);
    // remove method with single parameter
    int value = numbers.remove("Two");
    System.out.println("Removed value: " + value);
    // remove method with two parameters
    boolean result = numbers.remove("Three", 3);
    System.out.println("Is the entry {Three=3} removed? " + result);
    System.out.println("Updated TreeMap: " + numbers);
  }
}
```

**Output**

```
TreeMap: {One=1, Three=3, Two=2}
Removed value = 2
Is the entry {Three=3} removed? True
Updated TreeMap: {One=1}
```

## 1.2.5 Replace TreeMap Elements

-   replace(key, value) - replaces the value mapped by the specified *key* with the new *value*
-   replace(key, old, new) - replaces the old value with the new value only if the old value is already associated with the specified key
-   replaceAll(function) - replaces each value of the map with the result of the specified *function*

**Example:**

```java
import java.util.TreeMap;
class Main {
  public static void main(String[] args) {
    TreeMap<String, Integer> numbers = new TreeMap<>();
    numbers.put("First", 1);
    numbers.put("Second", 2);
    numbers.put("Third", 3);
    System.out.println("Original TreeMap: " + numbers);
    // Using replace()
    numbers.replace("Second", 22);
    numbers.replace("Third", 3, 33);
    System.out.println("TreeMap using replace: " + numbers);
    // Using replaceAll()
    numbers.replaceAll((key, oldValue) -> oldValue + 2);
    System.out.println("TreeMap using replaceAll: " + numbers);
  }
}
```

**Output**

```
Original TreeMap: {First=1, Second=2, Third=3}
TreeMap using replace(): {First=1, Second=22, Third=33}
TreeMap using replaceAll(): {First=3, Second=24, Third=35}
```

-   Here, we have passed a lambda expression as an argument.
-   The replaceAll() method accesses all the entries of the map.
-   It then replaces all the elements with the new values (returned from the lambda expression).

## Loop Through an TreeMap

**1) Iterate TreeMap keys using forEach**

```java
import java.util.Set;
import java.util.TreeMap;
 
public class TreeMapForEachExample {
 
    public static void main(String[] args) {
        
        TreeMap<Integer, String> tmapColors = new TreeMap<Integer, String>();
        
        tmapColors.put(1, "Red");
        tmapColors.put(2, "Green");
        tmapColors.put(3, "Blue");
        
        /*
         * Get all keys using the keySet method
         */
        Set<Integer> keys = tmapColors.keySet();
        
        //iterate using forEach
        keys.forEach( key -> {            
            System.out.println(key);
        });
    }
}
```

**Output:**

```
1
2
3
```

**2) Iterate TreeMap values using forEach**

```java
import java.util.Collection;
import java.util.TreeMap;
 
public class TreeMapForEachExample {
 
    public static void main(String[] args) {
        
        TreeMap<Integer, String> tmapColors = new TreeMap<Integer, String>();
        
        tmapColors.put(1, "Red");
        tmapColors.put(2, "Green");
        tmapColors.put(3, "Blue");
        
        /*
         * Get all values using the values method
         */
        Collection<String> values = tmapColors.values();
        
        //iterate values using forEach
        values.forEach( value -> { 
            System.out.println( value );
        });
    }
}
```

**Output:**

```
Red
Green
Blue
```

**3) Iterate TreeMap entries using forEach**

```java
import java.util.Map;
import java.util.Set;
import java.util.TreeMap;
 
public class TreeMapForEachExample {
 
    public static void main(String[] args) {
        
        TreeMap<Integer, String> tmapColors = new TreeMap<Integer, String>();
        
        tmapColors.put(1, "Red");
        tmapColors.put(2, "Green");
        tmapColors.put(3, "Blue");
        
        /*
         * Get all entries using the entrySet method
         */
        Set<Map.Entry<Integer, String>> entries = tmapColors.entrySet();
        
        //iterate entries using the forEach
        entries.forEach( entry -> {
            System.out.println(entry.getKey() + "->" + entry.getValue());
        });        
    }
}
```

**Output:**

```
1->Red
2->Green
3->Blue
```

**4)Loop through an TreeMap with Iterator.**

**Example:**

```java
import java.util.*;
public class JavaExample{
  public static void main(String args[]){
    TreeMap<Integer, String> hmap = new TreeMap<>();

    //key and value pairs
    hmap.put(101, "Chaitanya");
    hmap.put(105, "Derick");
    hmap.put(111, "Logan");
    hmap.put(120, "Paul");

    //print HashMap elements
    Set set = hmap.entrySet();
    Iterator iterator = set.iterator();
    while(iterator.hasNext()) {
      Map.Entry m = (Map.Entry)iterator.next();
      System.out.print("key is: "+ m.getKey() + " & Value is: ");
      System.out.println(m.getValue());
    }
  }
}
```

**Output:**

```
Key is: 101 & value is: Chaitanya
Key is: 105 & value is: Derick
Key is: 111 & value is: Logan
Key is: 120 & value is: Paul
```

## 1.3 LinkedHashMap

-   The **LinkedHashMap** is just like HashMap with an additional feature of maintaining an order of elements inserted into it.
-   HashMap provided the advantage of quick insertion, search, and deletion but it never maintained the track and order of insertion which the LinkedHashMap provides where the elements can be accessed in their insertion order.

**Important Features of a LinkedHashMap:**

-   A LinkedHashMap contains values based on the key. It implements the Map interface and extends the HashMap class.
-   It contains only unique elements.
-   It may have one null key and multiple null values.
-   It is non-synchronized.
-   It is the same as HashMap with an additional feature that it maintains insertion order.
-   Following image shows graphical representation of How LinkedHashMap works internally.
-   LinkedHashMap extends Node class of HashMap and contains two more variable **before** and **after** to hold the before and after references of Entry object.

![https://1.bp.blogspot.com/-fW_E_QPoc0E/XeDe5AhRZVI/AAAAAAAAGkE/Kh2Pl0U6ibkSezgh9e7i3fM2raciXE-bwCLcBGAsYHQ/s1600/How%2BLinkedHashMap%2Bworks.png](media/linkedhashmap.png)

**Example:**

```java
import java.util.*;
public class JavaExample{
  public static void main(String args[]){
    LinkedHashMap<Integer, String> hmap = new LinkedHashMap<>();

    //key and value pairs
    hmap.put(100, "Chaitanya");
    hmap.put(120, "Paul");
    hmap.put(105, "Derick");
    hmap.put(111, "Logan");

    //print LinkedHashMap elements
    Set set = hmap.entrySet();
    Iterator iterator = set.iterator();
    while(iterator.hasNext()) {
      Map.Entry m = (Map.Entry)iterator.next();
      System.out.print("key is: "+ m.getKey() + " & Value is: ");
      System.out.println(m.getValue());
    }
  }
}
```

**Output:**

```
key is: 100 & Value is: Chaitanya
key is: 120 & Value is: Paul
key is: 105 & Value is: Derick
key is: 111 & Value is: Logan
```

## 2. References

1.  https://beginnersbook.com/java-collections-tutorials/
2.  https://www.w3schools.com/java/java_hashmap.asp
3.  https://www.javaquery.com/2019/12/how-linkedhashmap-works-internally-in.html
4.  https://www.programiz.com/java-programming/map
5.  https://www.digitalocean.com/community/tutorials/java-hashmap
6.  https://prutor.ai/linkedhashmap-in-java/
