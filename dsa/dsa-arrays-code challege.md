## DS&A: Arrays Code Challenge

-   java provides a data structure, the **array**, which stores a fixed-size sequential collection of elements of the same type.
-   An array is used to store a collection of data, but it is often more useful to think of an array as a collection of variables of the same type.
-   Instead of declaring individual variables, such as number0, number1, ..., and number99, you declare one array variable such as numbers and use numbers[0], numbers[1], and ..., numbers[99] to represent individual variables.
-   This tutorial introduces how to declare array variables, create arrays, and process arrays using indexed variables.

## Declaring Array Variables

-   To use an array in a program, you must declare a variable to reference the array, and you must specify the type of array the variable can reference. Here is the syntax for declaring an array variable –

**Syntax**

dataType[] arrayRefVar; // preferred way.

or

dataType arrayRefVar[]; // works but not preferred way.

**Note** − The style **dataType[] arrayRefVar** is preferred. The style **dataType arrayRefVar[]** comes from the C/C++ language and was adopted in Java to accommodate C/C++ programmers.

**Example**

double[] myList; // preferred way.

Or

Double myList[]; //works abut not preferred way

## Creating Arrays

You can create an array by using the new operator.

**Syntax**

arrayRefVar = new dataType[arraySize];

<https://www.geeksforgeeks.org/overview-of-data-structures-set-1-linear-data-structures/?ref=lbp>

https://www.simplilearn.com/tutorials/data-structure-tutorial/arrays-in-data-structure\#:\~:text=the%20same%20kind.-,What%20Are%20Arrays%20in%20Data%20Structures%3F,the%20size%20of%20the%20array.
