## DS&A: Arrays Code Challenge

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

### Example

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

<https://www.geeksforgeeks.org/overview-of-data-structures-set-1-linear-data-structures/?ref=lbp>

https://www.simplilearn.com/tutorials/data-structure-tutorial/arrays-in-data-structure\#:\~:text=the%20same%20kind.-,What%20Are%20Arrays%20in%20Data%20Structures%3F,the%20size%20of%20the%20array.
