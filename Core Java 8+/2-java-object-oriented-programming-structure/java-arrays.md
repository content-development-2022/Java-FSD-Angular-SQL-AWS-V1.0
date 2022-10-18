# Java Arrays

**Content**

## 1. Java Arrays

-   Java provides a data structure, the **array**, which stores a fixed-size sequential collection of elements of the same type.
-   Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value.
-   The elements of an array are stored in a contiguous memory location.

    ![](media/ab5e32e7a5a1a3218f00c65bcf6233a1.png)

## 1.1 Declaring Array Variables

-   To use an array in a program, you must declare a variable to reference the array, and you must specify the type of array the variable can reference.

**Syntax:**

![](media/e96e3225f4d7e3b2cea22b23aacc7367.png)

-   **dataType -** it can be primitive data types like int, char, double, byte, etc. or Java objects
-   **arrayName -** it is an identifier

**Example-1:**

![](media/4ab9355f2b32e4af04f4a5dcbac7bdc4.png)

-   Here, data is an array that can hold values of type double.

**But, how many elements can array this hold?**

-   Good question! To define the number of elements that an array can hold, we have to allocate memory for the array in Java.

**Example-2:**

![](media/538c804c1d14855bb8b2236949dddc68.png)

-   Here, the array can store **10** elements. We can also say that the **size or length** of the array is 10.
-   In Java, we can declare and allocate the memory of an array in one single statement.

**Syntax:**

**![](media/40748bd63bbd409993cf723bfcbb2e0a.png)**

-   The above statement does two things :
1.  It creates an array using new dataType[arraySize].
2.  It assigns the reference of the newly created array to the variable arrayRefVar.

**Example-3:**

![](media/600a0ec951c7c9b4756c038462d2d667.png)

## 1.2 How to Initialize Arrays in Java?

-   In Java, we can initialize arrays during declaration.

**Example-1:**

![](media/b5ace3a1cf731ebd1898fadcbc883e00.png)

-   Here, we have created an array named age and initialized it with the values inside the curly brackets.
-   Note that we have not provided the size of the array.
-   In this case, the Java compiler automatically specifies the size by counting the number of elements in the array (i.e. 5).
-   In the Java array, each memory location is associated with a number.
-   The number is known as an array index.
-   We can also initialize arrays in Java, using the index number.

**Example-2:**

![](media/a8e2edb42e5282c0e51335db737d58f7.png)

![](media/091994d8dd74642ea25e42e16c9a3759.png)

## 1.3 Access the Elements of an Array in Java

-   We can access the element of an array using the index number.

**Syntax:**

![](media/7620958d54f047f8fbbb6f71c37b97a0.png)

**Example:**

![](media/24a27658f2f5535af3a34a373e3f16d9.png)

**Output:**

![](media/1c4cb46d85bb21e98593e9d147583e09.png)

-   In the above example, notice that we are using the index number to access each element of the array.
-   We can use loops to access all the elements of the array at once.

## 1.4 Change an Array Element

-   To change the value of a specific element, refer to the index number:

    ![](media/f7fb0699fd295f241782b9835486f7d1.png)

## 1.5 Array Length

-   To find out how many elements an array has, use the length property:

![](media/5be40a768e13e880c8dfa3ba8c85b3ef.png)

## 1.6 Advantages of array

**1) Code Optimization**

-   It makes the code optimized, we can retrieve or sort the data efficiently.

**2) Random access**

-   We can get any data located at an index position.

## 1.7 Disadvantages of array

**1) Size Limit**

-   We can store only the fixed size of elements in the array.
-   It doesn’t grow its size at runtime.
-   To solve this problem, collection framework is used in Java which grows automatically.

# 2. Java Arrays Loop

## 2.1 Array with for Loop

-   You can loop through the array elements with the for loop, and use the length property to specify how many times the loop should run.

    **Example:**

**![](media/44cb56f89cb7e8f4103ed3d0f1e19c76.png)**

## 2.2 Array with For-Each

-   There is also a "**for-each**" loop, which is used exclusively to loop through elements in arrays:

**Syntax:**

**![](media/6a8c5bbf8c8e78d48a3729ce2b2bf5d3.png)**

**Example:**

**![](media/b782d71d580f2ea48e66f21caf03268c.png)**

-   The example above can be read like this: **for each** String element (called **i** - as in **i**ndex) in **cars**, print out the value of **i**.
-   If you compare the for loop and **for-each** loop, you will see that the **for-each** method is easier to write, it does not require a counter (using the length property), and it is more readable.

## Types of Array in java

There are two types of array.

-   Single Dimensional Array
-   Multidimensional Array

## 2.1 Single Dimensional Array in Java

-   It also known as a linear array, the elements are stored in a single row.

**Example:**

![](media/82ec8b3109e8494da354d52b0ffbd4e4.png)

![](media/c84f479eaa36fd0608460b29f3e5b444.png)

**Output:**

**![](media/6251a13d4b45dc9725e83103325cf4a3.png)**

![](media/efdceb5d030441127337ebb3a834cbda.png)

**Output:**

**![](media/841a43373315a97ae317dd647bb2e01e.png)**

## Multidimensional Array in Java

Two-dimensional arrays store the data in rows and columns:

![](media/b0ecce6646fd3fef094ed1f24ed0f76a.png)

In such case, data is stored in row and column based index (also known as matrix form).

**![](media/87b2caca456433b5bfb4f7db469fc71f.png)**

**Example to instantiate Multidimensional Array in Java**

**![](media/53f88dcbf50898076bda8ef8f13fc60d.png)**

### Example of Multidimensional Java Array

Let's see the simple example to declare, instantiate, initialize and print the 2Dimensional array.

**![](media/bc7f9757f9a396668e934b1c42799f29.png)**

**Output:**

**![](media/b35e7b166a6e8fa4a451c380b8d62deb.png)**

# How to Create Array of Objects in Java

In this section, we will learn **how to create and initialize an array of objects in Java**.

## Array of Objects in Java

Java is an object-oriented programming language. Most of the work done with the help of **objects**. We know that an array is a collection of the same data type that dynamically creates objects and can have elements of primitive types. Java allows us to store objects in an array. In Java

, the class is also a user-defined data type. An array that conations **class type elements** are known as an **array of objects**. It stores the reference variable of the object.

![](media/f640edb9107b926e1110cf61b3530537.png)

## Creating an Array of Objects

Before creating an array of objects, we must create an instance of the class by using the new keyword. We can use any of the following statements to create an array of objects.

**Syntax:**

![](media/ecfb90f532791dbcdde930dbd7c969c5.png)

Or

![](media/80e53cc9b0c19bdd49fa7e46a6ba73cc.png)

Or

![](media/5a839fff60ff809bb49de2a434e74254.png)

Suppose, we have created a class named Employee. We want to keep records of 20 employees of a company having three departments. In this case, we will not create 20 separate variables. Instead of this, we will create an array of objects, as follows.

![](media/0b68337bbca9d0e3d7a4af6aa71fdddb.png)

The above statements create an array of objects with 20 elements.

Let's create an array of objects in a Java program

.

In the following program, we have created a class named Product and initialized an array of objects using the constructor. We have created a constructor of the class Product that contains product id and product name. In the main function, we have created individual objects of the class Product. After that, we have passed initial values to each of the objects using the constructor.

**ArrayOfObjects.java**

![](media/7cf47d4f583660b4974ccb49ad24092d.png)

## References

https://www.w3schools.com/java/java_arrays.asp

https://www.javatpoint.com/array-in-java

https://www.programiz.com/java-programming/arrays
