# Java Arrays

**Content**

1\. Arrays in Java

2\. Types of Arrays in java

2.1 Single Dimensional Array in Java

2.1.1 Declaring 1D Array Variables in Java

2.1.2 Initializing 1D Array in Java

2.1.3 Accessing 1D Array elements in Java

2.1.4 Iterating/Traversing 1D Arrays in Java

2.1.5 Change an 1D Array Element

2.1.6 1D Array Length

2.2 Multiple Dimensional Array in Java

2.2.1 Declaring Multiple Dimensional Array Variables in Java

2.2.2 Two Dimensional Array in Java

2.2.2.1 Declaring 2D Array Variables in Java

2.2.2.2 Initializing 2D Array in Java

2.2.2.3 Accessing 2D Array elements in Java

2.2.2.4 Iterating/Traversing 2D Array in Java

2.3 Advantages of array

2.4 Disadvantages of array

3\. Jagged Array in Java

3.1 Declaration and Initialization of Jagged array in java

4\. Array of Objects in Java

4.1 Declaring an Array of Objects in Java

4.2 Instantiate an Array of Objects in Java

4.3 Initializing Array o**f Objects**

4.3.**1** By using the constructor

4.3.2 By using a separate member method

5\. References

## 1. Arrays in Java

-   Java provides a data structure, the **array**, which stores a fixed-size sequential collection of elements of the same type.
-   Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value.
-   The elements of an array are stored in a contiguous memory location.

**Note:**

-   Array indices always start from 0. That is, the first element of an array is at index 0.
-   If the size of an array is n, then the last element of the array will be at index n-1.

## 2. Types of Arrays in java

There are two types of arrays.

-   Single Dimensional Array
-   Multidimensional Array

## 2.1 Single Dimensional Array in Java

-   Single dimensional array of Java is a normal array where, the array contains sequential elements (of same type).
-   It is also known as a linear array or 1D or one Dimensional array, the elements are stored in a single row.
-   One dimensional array use single index to store elements.

## 2.1.1 Declaring 1D Array Variables in Java

-   To use an array in a program, you must declare a variable to reference the array, and you must specify the type of array the variable can reference.

**Syntax:**

![](media/451ff2ee4e5e511dd0792400f166e612.png)

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

## 2.1.2 Initializing 1D Array in Java

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

## 2.1.3 Accessing 1D Array elements in Java

-   We can access the element of an array using the index number.

**Syntax:**

![](media/7620958d54f047f8fbbb6f71c37b97a0.png)

**Example:**

![](media/24a27658f2f5535af3a34a373e3f16d9.png)

**Output:**

![](media/1c4cb46d85bb21e98593e9d147583e09.png)

-   In the above example, notice that we are using the index number to access each element of the array.
-   We can use loops to access all the elements of the array at once.

# 2.1.4 Iterating/Traversing 1D Arrays in Java

**1) 1D Array with for Loop**

-   You can loop through the array elements with the **for** loop, and use the **length** property to specify how many times the loop should run.

    **Example:**

**![](media/44cb56f89cb7e8f4103ed3d0f1e19c76.png)**

**2) 1D Array with for-each**

-   There is also a "**for-each**" loop, which is used exclusively to loop through elements in arrays:

**Syntax:**

**![](media/6a8c5bbf8c8e78d48a3729ce2b2bf5d3.png)**

**Example:**

**![](media/b782d71d580f2ea48e66f21caf03268c.png)**

-   The example above can be read like this: **for each** String element (called **i** - as in **i**ndex) in **cars**, print out the value of **i**.
-   If you compare the for loop and **for-each** loop, you will see that the **for-each** method is easier to write, it does not require a counter (using the length property), and it is more readable.

## 2.1.5 Change an 1D Array Element

-   To change the value of a specific element, refer to the index number:

    ![](media/f7fb0699fd295f241782b9835486f7d1.png)

## 2.1.6 1D Array Length

-   To find out how many elements an array has, use the length property:

![](media/5be40a768e13e880c8dfa3ba8c85b3ef.png)

## 2.2 Multiple Dimensional Array in Java

-   A multidimensional array is an array of arrays.
-   It is also known as N-Dimensional array.

## 2.2.1 Declaring Multiple Dimensional Array Variables in Java

**Syntax:**

![](media/78c18287a86ede96523c0bce5547839d.png)

**where:**

-   **data_type**: Type of data to be stored in the array.
-   **dimension**: The dimension of the array created. For example: 1D, 2D, 3D etc.
-   **array_name**: Name of the array
-   **size1, size2, …, sizeN**: Sizes of the dimensions respectively.

**Example**:

![](media/6c50700b66d32692923d2505c0f4e0d3.png)

**Size of multidimensional arrays**

-   The total number of elements that can be stored in a multidimensional array can be calculated by multiplying the size of all the dimensions.

**Example:**

**int[][][] x = new int[5][10][20]** can store a total of (5\*10\*20) = 1000 elements.

-   Two – dimensional array is the simplest form of a multidimensional array.

## 2.2.2 Two Dimensional Array in Java

-   In Java, the tabular representation of data is implemented using a two-dimensional array.
-   The 2D array is organized as matrices which can be represented as the collection of rows and columns.

![](media/7251eef492cb6657dccffd0f906a2e36.png)

## 2.2.2.1 Declaring 2D Array Variables in Java

-   A 2D array consists of rows and columns, we need two indices, one to refer rows and the other to a particular column in that row.
-   Hence, the syntax of declaring a 2D array is similar to that of a one-dimensional array with the exception of having two square brackets instead of one:

    ![](media/0ab00b4c5b1058dc19150741028378ca.png)

-   The above-described syntax only declares the array i.e., the memory is allocated for the array object but the values will be added later.

**Example:**

![](media/cd9ce59120e5320dcf0eea9171d0557e.png)

-   To create a 2D array object we need to use the new keyword as shown below:

![](media/b34210ce5de5905f80431812d79b2e58.png)

-   Here, the new DataType[r][c] statement creates a 2D array object that contains r rows and c columns and elements of DataType type.
-   This array object is referenced by the reference variable ArrayName.

**Example:**

![](media/7a6640b99a934f541048dd3bf5696357.png)

-   In Java, we can declare and allocate the memory of an array in one single statement.

**Syntax:**

![](media/48ecfe0e0d017e79660427feeda016f1.png)

**Note:**

-   When we create a 2D array object using the new keyword, the JVM (Java Virtual Machine) allocates the memory required for the 2D array and initializes the memory spaces with the default values according to the data type of the array object.
-   For example, in the case of the Integer array (int[][]), every element of the array is initialized with the default value of 0.

    ![](media/ed9dab7b91b636c5c08a55f94bab8b0e.png)

## 2.2.2.2 Initializing 2D Array in Java

-   Once the array is declared and created, it is time to initialize it with values.
-   There are two methods of initializing the 2D array with values.

**Method1:**

-   The first method is the traditional method of assigning values to each element.

**Syntax:**

![](media/72886de72263430e6cb741249f73c2c2.png)

**Example:**

int[][] myarray = new int[2][2];

myarray[0][0] = 1;

myarray[0][1] = myarray[1][0] = 0;

myarray[1][1] = 1;

**Method2:**

**Syntax:**

**![](media/08d5ab62dd3bcbf0c04c81c890b818a9.png)**

**Example:**

**![](media/7099ac20caa0d6e6648bfd9852e95462.png)**

## 2.2.2.3 Accessing 2D Array elements in Java

-   We can directly access any element from an array using indexing.
-   In the case of 2D arrays, we use row and column indices to access a particular element from the matrix.

**Syntax:**

![](media/09215a3464dba3d257a4d51382225bf2.png)

-   Here, the ArrayName[i][j] statement is used to access the element present at the intersection of **i**th row and **j**th column in the 2D array ArrayName.

**Example:**

![](media/bfe30c47384e43465251ab729595fc17.png)

**Note :**

-   We can only access the elements of an array using positive integer as the index.
-   We can't use negative indices to access any elements from an array in Java.
-   If we pass an index that is greater than the size of the array (out of bounds index), the ArrayIndexOutOfBoundsException error will occur.

# 2.2.2.4 Iterating/Traversing 2D Array in Java

**1) 2D Array with for Loop**

**Example:**

**![](media/6cb4284b4a5a885f37440be16c7d2f98.png)**

**Output:**

**![](media/38e33c8c26d96ae067d29b85ec6a3e46.png)**

**2) 2D Array with for-each**

**Example:**

![](media/47d53779acb537c1f3b9cb44082fe2e8.png)

**Output:**

![](media/33d7fb046c4f89ba0a1b8f660236f212.png)

## 2.3 Advantages of array

**1) Code Optimization**

-   It makes the code optimized, we can retrieve or sort the data efficiently.

**2) Random access**

-   We can get any data located at an index position.

## 2.4 Disadvantages of array

**1) Size Limit**

-   We can store only the fixed size of elements in the array.
-   It doesn’t grow its size at runtime.
-   To solve this problem, collection framework is used in Java which grows automatically.

## 3. Jagged Array in Java

-   Jagged arrays are also known as ragged or irregular arrays.
-   A Jagged Array is defined as an array where each element of that array is an array itself.
-   It is a Multidimensional array whose each element can have different sizes.

![](media/efe60febd2d7fd659d7c5a2ce9cbfb57.png)

-   From the above pictorial representation, we got an idea of how does it look.
-   Above shown is a two-dimensional Jagged array.
-   Each individual element of this array is a one-dimensional array that has varied sizes as shown above.
-   The first 1D array has 3 columns; the second row has 2 columns while the third has 4 columns.

## 3.1 Declaration and Initialization of Jagged array in java

-   While creating an array of arrays you only specify the first dimension that represents a number of rows in the array.

**Syntax:**

![](media/a2eda1111757917615ffe3fa905bf131.png)

-   **Alternative, ways to Initialize a Jagged array**

![](media/4702caf26ba9d64fc6d82765c896b2c1.png)

**Example:**

![](media/7c1fe655ab2e7e64b723ab40dd7c932d.png)

**Output:**

![](media/86ad186500fd9f06af9931517ff9d112.png)

## 4. Array of Objects in Java

-   Java is an object-oriented programming language.
-   Most of the work done with the help of **objects**.
-   We know that an array is a collection of the same data type that dynamically creates objects and can have elements of primitive types.
-   Java allows us to store objects in an array.
-   In Java, the class is also a user-defined data type.
-   An array that conations **class type elements** are known as an **array of objects**.
-   It stores the reference variable of the object.

![](media/f640edb9107b926e1110cf61b3530537.png)

## 4.1 Declaring an Array of Objects in Java

-   An Array of Objects is created using the Object class, and we know Object class is the root class of all Classes.
-   We use the *Class_Name* followed by a square bracket *[]* then object reference name to create an Array of Objects.

**Syntax:**

![](media/80e53cc9b0c19bdd49fa7e46a6ba73cc.png)

-   Alternatively, we can also declare an Array of Objects as:

![](media/5a839fff60ff809bb49de2a434e74254.png)

**Example:**

![](media/d3b629fda320e1e50bcb9b1fd024ed57.png)

## 4.2 Instantiate an Array of Objects in Java

**Syntax:**

![](media/ecfb90f532791dbcdde930dbd7c969c5.png)

-   For example, if you have a class Student, and we want to declare and instantiate an array of Student objects with two objects/object references then it will be written as:

![](media/570b403fd62af20e3152459bd47e5bd7.png)

-   Once an array of objects is instantiated like this, then the individual elements of the array of objects needs to be created using the new keyword.
-   The below figure shows the structure of an Array of Objects :

![](media/53d268e37e63aa4efcf398a7bebea98d.png)

## 4.3 Initializing Array of Objects

-   Once the array of objects is instantiated, we need to initialize it with values.
-   We cannot initialize the array in the way we initialize with primitive types as it is different from an array of primitive types.
-   In an array of objects, we have to initialize each element of array i.e. each object/object reference needs to be initialized.

**Different ways to initialize the array of objects:**

1.  By using the constructors
2.  By using a separate member method

## 4.3.1 By using the constructor

-   At the time of creating actual objects, we can assign initial values to each of the objects by passing values to the constructor separately.
-   Individual actual objects are created with their distinct values.

**Example:**

![](media/91715ca4fc927cb3d55b7d25aa8cf484.png)

**Output:**

![](media/75e5b54fabc3a9b05e1ada401161d818.png)

## 4.3.2 By using a separate member method

-   By using a separate member method also we can initialize objects.
-   A member function of the respective class is created and that is used to assign the initial values to the objects.

**Example:**

![](media/375808d81943eeae6c22c54cacd9769c.png)

**Output:**

![](media/cb49fa48c8776531dbcae7c03526b0ab.png)

## 5. References

1.  https://www.w3schools.com/java/java_arrays.asp
2.  https://www.javatpoint.com/array-in-java
3.  https://www.programiz.com/java-programming/arrays
4.  https://www.scaler.com/topics/two-dimensional-array-in-java/
5.  https://www.softwaretestinghelp.com/jagged-array-in-java/
6.  https://www.geeksforgeeks.org/jagged-array-in-java/
