## 

# Collection List

**Content**

1\. List

1.1 ArrayList

1.2 LinkedList

1.3 Vector

1.4 Stack

2\. References

## 1. List

-   A List is an ordered Collection (sometimes called a sequence).
-   Lists may contain duplicate elements.
-   Elements can be inserted or accessed by their position in the list, using a zero-based index.

**The classes that implements List interface are:**

-   ArrayList
-   LinkedList
-   Vector
-   Stack

## 1.1 ArrayList

-   ArrayList is a popular alternative of arrays in Java.
-   It is based on an Array **data structure**.
-   ArrayList is a resizable-array implementation of the List interface.
-   It implements all optional list operations, and permits all elements, including null.
-   *ArrayList* resides within Java Core Libraries, so you don't need any additional libraries.
-   In order to use it just add the following import statement:

```java
import java.util.ArrayList;
```

**1) Create an ArrayList**

-   Create an ArrayList object called **cars** that will store strings:

**Example:**

```java
import java.util.ArrayList; // import the ArrayList class
ArrayList<String> cars = new ArrayList<String>(); // Create an ArrayList object
```

**2) Add Elements to the ArrayList**

-   You may insert an element either at the end or at the specific position:

**Example:**

```java
import java.util.ArrayList;
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    System.out.println(cars);
  }
}
```

**Output:**

```
[Volvo, BMW, Ford, Mazda]
```

**3) Access an Item**

-   To access an element in the ArrayList, use the get() method and refer to the index number:

**Example:**

```java
import java.util.ArrayList;
public class Main { 
  public static void main(String[] args) { 
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    System.out.println(cars.get(0));
  } 
}
```

**Output:**

```
Volvo
```

**Remember:** Array indexes start with 0: [0] is the first element. [1] is the second element, etc.

**4) Change an Item**

-   To modify an element, use the set() method and refer to the index number:

**Example:**

```java
import java.util.ArrayList;
public class Main { 
  public static void main(String[] args) { 
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    cars.set(0, "Opel");
    System.out.println(cars);
  } 
}
```

**Output:**

```
[Opel, BMW, Ford, Mazda]
```

**5) Remove an Item**

-   To remove an element, use the remove() method and refer to the index number:

**Example:**

```java
import java.util.ArrayList;
public class Main { 
  public static void main(String[] args) { 
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    cars.remove(0);
    System.out.println(cars);
  } 
}
```

**Output:**

```
[BMW, Ford, Mazda]
```

-   To remove all the elements in the ArrayList, use the clear() method:

**Example:**

```java
import java.util.ArrayList;
public class Main { 
  public static void main(String[] args) { 
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    cars.clear();
    System.out.println(cars);
  } 
}
```

**Output:**

```
[]
```

**6) ArrayList Size**

-   To find out how many elements an ArrayList have, use the size method:

```java
cars.size();
```

**7) Loop Through an ArrayList**

-   Loop through the elements of an ArrayList with a for loop, and use the size() method to specify how many times the loop should run:

**Example:**

```java
import java.util.ArrayList;
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    for (int i = 0; i < cars.size(); i++) {
      System.out.println(cars.get(i));
    }
  }
}
```

**Output:**

```
Volvo
BMW
Ford
Mazda
```

-   You can also loop through an ArrayList with the **for-each** loop:

**Example:**

```java
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    for (String i : cars) {
      System.out.println(i);
    }
  }
}
```

**Output:**

```
Volvo
BMW
Ford
Mazda
```

**8) Sort an ArrayList**

-   Another useful class in the java.util package is the Collections class, which include the sort() method for sorting lists alphabetically or numerically:

**i) Sort an ArrayList of Strings:**

**Example:**

```java
import java.util.ArrayList;
import java.util.Collections;  // Import the Collections class
public class Main {
  public static void main(String[] args) {
    ArrayList<String> cars = new ArrayList<String>();
    cars.add("Volvo");
    cars.add("BMW");
    cars.add("Ford");
    cars.add("Mazda");
    Collections.sort(cars);  // Sort cars
    for (String i : cars) {
      System.out.println(i);
    }
  }
}
```

**Output:**

```
BMW
Ford
Mazda
Volvo
```

**ii) Sort an ArrayList of Integers:**

**Example:**

```java
import java.util.ArrayList;
import java.util.Collections;  // Import the Collections class
public class Main {
  public static void main(String[] args) {
    ArrayList<Integer> myNumbers = new ArrayList<Integer>();
    myNumbers.add(33);
    myNumbers.add(15);
    myNumbers.add(20);
    myNumbers.add(34);
    myNumbers.add(8);
    myNumbers.add(12);

    Collections.sort(myNumbers);  // Sort myNumbers

    for (int i : myNumbers) {
      System.out.println(i);
    }
  }
}
```

**Output:**

```
8
12
15
20
33
34
```

## 1.2 LinkedList

-   LinkedList is a linear data structure.
-   LinkedList elements are not stored in contiguous locations like arrays, they are linked with each other using pointers.
-   Each element of the LinkedList has the reference(address/pointer) to the next element of the LinkedList.

![](media/linked-list.png)

**Example:**

```java
import java.util.*;
public class JavaExample{
  public static void main(String args[]){
    LinkedList<String> linkList=new LinkedList<>();
    linkList.add("Apple"); //["Apple"]
    linkList.add("Orange"); //["Apple", "Orange"]

    //inserting element at first position
    linkList.add(0, "Banana"); ////["Banana", "Apple", "Orange"]

    System.out.println("LinkedList elements: ");
    //iterating LinkedList using iterator
    Iterator<String> it=linkList.iterator();
    while(it.hasNext()){
      System.out.println(it.next());
    }
  }
}
```

**Output:**

```
LinkedList elements:
Banana
Apple
Orange
```

## 1.3 Vector

**Example:**

```java
import java.util.*;
public class JavaExample{
  public static void main(String args[]){
    Vector<String> v=new Vector<>();
    v.add("item1"); //["item1"]
    v.add("item2"); //["item1", "item2"]
    v.add("item3"); //["item1", "item2", "item3"]

    //removing an element
    v.remove("item2"); //["item1", "item3"]

    System.out.println("Vector Elements: ");
    //iterating Vector using iterator
    Iterator<String> it=v.iterator();
    while(it.hasNext()){
      System.out.println(it.next());
    }
  }
}
```

**Output:**

```
Vector Elements:
item1
item3
```

## 1.4 Stack

-   Stack class extends Vector class, which means it is a subclass of Vector.
-   Stack works on the concept of Last In First Out (LIFO).
-   The elements are inserted using push() method at the end of the stack, the pop() method removes the element which was inserted last in the Stack.

**Example:**

```java
import java.util.*;
public class JavaExample{
  public static void main(String args[]){
    Stack<String> stack = new Stack<>();

    //push() method adds the element in the stack
    //and pop() method removes the element from the stack
    stack.push("Chaitanya"); //["Chaitanya"]
    stack.push("Ajeet"); //["Chaitanya", Ajeet]
    stack.push("Hari"); //["Chaitanya", "Ajeet", "Hari"]
    stack.pop(); //removes the last element
    stack.push("Steve"); //["Chaitanya", "Ajeet", "Steve"]
    stack.push("Carl"); //["Chaitanya", "Ajeet", "Steve", "Carl"]
    stack.pop(); //removes the last element

    System.out.println("Stack elements: ");
    for(String str: stack){
      System.out.println(str);
    }
  }
}
```

**Output:**

```
Stack elements:
Chaitanya
Ajeet
Steve
```

## 2. References

1.  https://beginnersbook.com/java-collections-tutorials/
2.  https://www.w3schools.com/java/java_arraylist.asp
