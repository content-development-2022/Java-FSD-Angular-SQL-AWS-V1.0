# DS&A

Contents

1.Java-Array

1.1 Declaring Array Variables

1.2 Creating Arrays

1.3 Processing Arrays

1.4 The Arrays Class

2.Java Data Structure

# Java - Array

-   java provides a data structure, the **array**, which stores a fixed-size sequential collection of elements of the same type.
-   An array is used to store a collection of data, but it is often more useful to think of an array as a collection of variables of the same type.
-   Instead of declaring individual variables, such as number0, number1, ..., and number99, you declare one array variable such as numbers and use numbers[0], numbers[1], and ..., numbers[99] to represent individual variables.
-   This tutorial introduces how to declare array variables, create arrays, and process arrays using indexed variables.

## Declaring Array Variables

-   To use an array in a program, you must declare a variable to reference the array, and you must specify the type of array the variable can reference. Here is the syntax for declaring an array variable –

**Syntax**

dataType[] arrayRefVar;

or

dataType arrayRefVar[];

**Note**:

-   The style **dataType[] arrayRefVar** is preferred. The style **dataType arrayRefVar[]** comes from the C/C++ language and was adopted in Java to accommodate C/C++ programmers.

**Example**

double[] myList; // preferred way.

Or

Double myList[]; //works abut not preferred way

## Creating Arrays

You can create an array by using the new operator.

**Syntax**

arrayRefVar = new dataType[arraySize];

-   The above statement does two things:
1.  It creates an array using new dataType[arraySize].
2.  It assigns the reference of the newly created array to the variable arrayRefVar.
-   Declaring an array variable, creating an array, and assigning the reference of the array to the variable can be combined in one statement, as shown below −

dataType[] arrayRefVar = new dataType[arraySize];

-   Alternatively you can create arrays as follows

dataType[] arrayRefVar = {value0, value1, ..., valuek};

-   The array elements are accessed through the **index**.
-   Array indices are 0-based; that is, they start from 0 to **arrayRefVar.length-1**.

### Example

Following statement declares an array variable, myList, creates an array of 10 elements of double type and assigns its reference to myList −

double[] myList = new double[10];

-   Following picture represents array myList. Here, myList holds ten double values and the indices are from 0 to 9.

![Java Array](media/aab3f072a85bd9024a2245021d37db17.jpeg)

## Processing Arrays

When processing array elements, we often use either **for** loop or **foreach** loop because all of the elements in an array are of the same type and the size of the array is known.

**Example**

Here is a complete example showing how to create, initialize, and process arrays

[Live Demo](http://tpcg.io/aXdX5u)

public class TestArray

{

public static void main(String[] args)

{

double[] myList = {1.9, 2.9, 3.4, 3.5};

// Print all the array elements

for (int i = 0; i \< myList.length; i++)

{

System.out.println(myList[i] + " ");

}

// Summing all elements

double total = 0;

for (int i = 0; i \< myList.length; i++)

{

total += myList[i];

}

System.out.println("Total is " + total);

// Finding the largest element

double max = myList[0];

for (int i = 1; i \< myList.length; i++)

{

if (myList[i] \> max)

max = myList[i];

}

System.out.println("Max is " + max);

}

}

### Output

1.9

2.9

3.4

3.5

Total is 11.7

Max is 3.5

## The Arrays Class

The java.util.Arrays class contains various static methods for sorting and searching arrays, comparing arrays, and filling array elements. These methods are overloaded for all primitive types.

| **Sr.No.** | **Method & Description**                                                                                                                                                                                                                                                                                                                                                                                                       |
|------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1          | **public static int binarySearch(Object[] a, Object key)** Searches the specified array of Object ( Byte, Int , double, etc.) for the specified value using the binary search algorithm. The array must be sorted prior to making this call. This returns index of the search key, if it is contained in the list; otherwise, it returns ( – (insertion point + 1)).                                                           |
| 2          | **public static boolean equals(long[] a, long[] a2)** Returns true if the two specified arrays of longs are equal to one another. Two arrays are considered equal if both arrays contain the same number of elements, and all corresponding pairs of elements in the two arrays are equal. This returns true if the two arrays are equal. Same method could be used by all other primitive data types (Byte, short, Int, etc.) |
| 3          | **public static void fill(int[] a, int val)** Assigns the specified int value to each element of the specified array of ints. The same method could be used by all other primitive data types (Byte, short, Int, etc.)                                                                                                                                                                                                         |
| 4          | **public static void sort(Object[] a)** Sorts the specified array of objects into an ascending order, according to the natural ordering of its elements. The same method could be used by all other primitive data types (Byte, short, Int, etc.)                                                                                                                                                                              |

# Java - Data Structures

-   The data structures provided by the Java utility package are very powerful and perform a wide range of functions.
-   These data structures consist of the following interface and classes.
1.  Enumeration
2.  BitSet
3.  Vector
4.  Stack
5.  Dictionary
6.  Hashtable
7.  Properties

## The Enumeration

-   The Enumeration interface isn't itself a data structure, but it is very important within the context of other data structures.
-   The Enumeration interface defines a means to retrieve successive elements from a data structure.
-   For example, Enumeration defines a method called nextElement that is used to get the next element in a data structure that contains multiple elements.
-   To have more detail about this interface, check [The Enumeration](https://www.tutorialspoint.com/java/java_enumeration_interface.htm).

## The BitSet

-   The BitSet class implements a group of bits or flags that can be set and cleared individually.
-   This class is very useful in cases where you need to keep up with a set of Boolean values; you just assign a bit to each value and set or clear it as appropriate.
-   For more details about this class, check [The BitSet](https://www.tutorialspoint.com/java/java_bitset_class.htm).

## The Vector

-   The Vector class is similar to a traditional Java array, except that it can grow as necessary to accommodate new elements.
-   Like an array, elements of a Vector object can be accessed via an index into the vector.
-   The nice thing about using the Vector class is that you don't have to worry about setting it to a specific size upon creation; it shrinks and grows automatically when necessary.
-   For more details about this class, check [The Vector](https://www.tutorialspoint.com/java/java_vector_class.htm).

## The Stack

-   The Stack class implements a last-in-first-out (LIFO) stack of elements.
-   You can think of a stack literally as a vertical stack of objects; when you add a new element, it gets stacked on top of the others.
-   When you pull an element off the stack, it comes off the top. In other words, the last element you added to the stack is the first one to come back off.
-   For more details about this class, check [The Stack](https://www.tutorialspoint.com/java/java_stack_class.htm).

## The Dictionary

-   The Dictionary class is an abstract class that defines a data structure for mapping keys to values.
-   This is useful in cases where you want to be able to access data via a particular key rather than an integer index.
-   Since the Dictionary class is abstract, it provides only the framework for a key-mapped data structure rather than a specific implementation.
-   For more details about this class, check [The Dictionary](https://www.tutorialspoint.com/java/java_dictionary_class.htm).

## The Hashtable

-   The Hashtable class provides a means of organizing data based on some user-defined key structure.
-   For example, in an address list hash table you could store and sort data based on a key such as ZIP code rather than on a person's name.
-   The specific meaning of keys with regard to hash tables is totally dependent on the usage of the hash table and the data it contains.
-   For more detail about this class, check [The Hashtable](https://www.tutorialspoint.com/java/java_hashtable_class.htm).

## The Properties

-   Properties is a subclass of Hashtable. It is used to maintain lists of values in which the key is a String and the value is also a String.
-   The Properties class is used by many other Java classes. For example, it is the type of object returned by System.getProperties( ) when obtaining environmental values.

<https://www.tutorialspoint.com/java/java_date_time.htm>

https://www.tutorialspoint.com/java/java_data_structures.htm

<https://www.geeksforgeeks.org/overview-of-data-structures-set-1-linear-data-structures/?ref=lbp>

https://www.simplilearn.com/tutorials/data-structure-tutorial/arrays-in-data-structure\#:\~:text=the%20same%20kind.-,What%20Are%20Arrays%20in%20Data%20Structures%3F,the%20size%20of%20the%20array.
