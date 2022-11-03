# Java Classes, Objects and Custom Class

**Content**

1\. Introduction

2\. What is a Class in Java?

2.1 Fields in Java?

2.2 What is a method in Java?

3\. What is an Object in Java?

3.1 What are the different ways to create an object in Java?

3.2 Ways to Initialize Object

4\. Create a Custom Class in Java

5\. Java Constructors

5.1 Rules for creating Java constructor

5.2 Types of Java constructors

5.2.1 Java Default Constructor

5.2.2 Java Parameterized Constructor

5.3 Constructor Overloading in Java

5.4. Difference between constructor and method in Java

5.5 Java Copy Constructor

5.5.1 Copying values with constructor

5.5.2 Copying values without constructor

6\. Introduction of Stack and Heap in Java

6.1 Stack Memory

6.2 Heap Memory

6.3 Difference between Stack and Heap Memory

7\. Java Garbage Collection

7.1 Advantage of Garbage Collection

7.2 How can an object be unreferenced?

8\. References

## 1. Introduction

-   In this document, we will learn about Java classes and objects.
-   In object-oriented programming technique, we design a program using classes and objects.
-   An object in Java is the physical as well as a logical entity, whereas, a class in Java is a logical entity only.

## 2. What is a Class in Java?

-   It is a template or blueprint from which objects are created.
-   It is a logical entity.
-   It can't be physical.

**A class in Java can contain:**

![](media/class-syntax.png)

**Syntax:**

```
class <class_name> {  
    field;  
    method;  
}  
```

## 2.1 Fields in Java

The fields in class are known as instance variables

-   Instance variables are declared in a class, but outside a method, constructor or any block.
-   When space is allocated for an object in the heap, a slot for each instance variable value is created.
-   Instance variables are created when an object is created with the use of the keyword 'new' and destroyed when the object is destroyed.
-   Instance variables hold values that must be referenced by more than one method, constructor or block, or essential parts of an object's state that must be present throughout the class.
-   Instance variables can be declared in a class level before or after use.
-   Access modifiers can be given for instance variables.
-   The instance variables are visible for all methods, constructors, and block in the class. Normally, it is recommended to make these variables private (access level). However, visibility for subclasses can be given for these variables with the use of access modifiers.
-   Instance variables have default values. For numbers, the default value is 0, for Booleans it is false, and for object references it is null. Values can be assigned during the declaration or within the constructor.
-   Instance variables can be accessed directly by calling the variable name inside the class. However, within static methods (when instance variables are given accessibility), they should be called using the fully qualified name. ObjectReference.VariableName.

**Syntax:**

```java
datatype variableName;
```

## 2.2 What is a method in Java?

-   A **method** is a block of code or collection of statements or a set of code grouped together to perform a certain task or operation.
-   The method is executed only when we call or invoke it.

**Advantages of methods**

-   It is used to achieve the **reusability** of code.
-   It also provides the **easy modification** and **readability** of code, just by adding or removing a chunk of code.

## 2.2.1 Method Defination

Syntax: Declare a method

```java
access_modifier return_type method_name( list_of_parameters) {

 //body of method

}
```

**Method Signature:** Every method has a method signature. It is a part of the method declaration. It includes the **method name** and **parameter list**.

**Access Specifier:** Access specifier or modifier is the access type of the method. It specifies the visibility of the method. Java provides **four** types of access specifier:

-   **Public:** The method is accessible by all classes when we use public specifier in our application.
-   **Private:** When we use a private access specifier, the method is accessible only in the classes in which it is defined.
-   **Protected:** When we use protected access specifier, the method is accessible within the same package or subclasses in a different package.
-   **Default:** When we do not use any access specifier in the method declaration, Java uses default access specifier by default. It is visible only from the same package only.

**Return Type:**

-   Return type is a data type that the method returns.
-   It may have a primitive data type, object, collection, void, etc.
-   If the method does not return anything, we use void keyword.

**Method Name:**

-   It is a unique name that is used to define the name of a method.
-   It must be corresponding to the functionality of the method.
-   Suppose, if we are creating a method for subtraction of two numbers, the method name must be **subtraction().**
-   A method is invoked by its name.

**Parameter List:**

-   It is the list of parameters separated by a comma and enclosed in the pair of parentheses.
-   It contains the data type and variable name.
-   If the method has no parameter, left the parentheses blank.

**Method Body:**

-   It is a part of the method declaration.
-   It contains all the actions to be performed.
-   It is enclosed within the pair of curly braces.

## 2.2.2 How to Call or Invoke a User-defined Method

-   Once we have defined a method, it should be called.
-   There are two ways in which a method is called i.e., method returns a value or returning nothing (no return value).
-   The calling of a method in a program is simple.
-   To call a method in Java, write the method's name followed by two parentheses **()** and a semicolon (;).
-   If the method has parameters in the declaration, those parameters are passed within the parentheses () but this time without their datatypes specified.
-   However, it is important to keep the sequence of arguments the same as defined in the method definition.
-   When we call or invoke a user-defined method, the program control transfer to the called method.

**Example:**

```java
public class Addition {
    public static void main(String[] args) {
    int a = 19;
    int b = 5;
    //method calling
    int c = add(a, b); //a and b are actual parameters
    System.out.println("The sum of a and b is= " + c);
    }
   
    //user defined method
    public static int add(int n1, int n2) { //n1 and n2 are formal parameters
        int s;
        s=n1+n2;
        return s; //returning the sum
    }
}
```

**Output:**

```
The sum of a and b is= 24
```

## 3. What is an Object in Java?

-   An object is *a* **real-world entity.**
-   An object is *a* **runtime entity.**
-   The object is *an* **entity** *which has* **state** *and* **behavior.**
-   The object is *an* **instance of a class**.
-   It can be physical or logical (tangible and intangible).

    ![](media/bc0a29a63f1c74c221a000820427945d.png)

-   **An object has three characteristics**

![](media/a0cdb7df386535eb418098f290d4b613.png)

**Example**: Pen is an object. Its name is Reynolds; color is white, known as its state. It is used to write, so writing is its behavior.

**Class and Object Example: main within the class**

-   In this example, we have created a Student class which has two data members **id** and **name**.
-   We are creating the object of the Student class by **new** keyword and printing the object's value.
-   Here, we are creating a main() method within the class.

**Example: Student.java**

![](media/d5d11010a2d5d04a2d990240160552cd.png)

**Output:**

![](media/40597e3184042fd6b18835b730a318c9.png)

**new keyword in Java**

-   The new keyword is used to allocate memory at runtime.
-   All objects get memory in Heap memory area.

**Class and Object Example: main outside the class**

-   We create classes and use it from another class.
-   It is a better approach than previous one.
-   We can have multiple classes in different Java files or single Java file.
-   If you define multiple classes in a single Java source file, it is a good idea to save the file name with the class name which has main() method.

**Example: TestStudent1.java**

![](media/7250707615b36a41a6b41958621bca90.png)

**Output:**

![](media/f93f50fc629c1856a73be1d5ab8252fd.png)

**Instance variable in Java**

-   A variable which is created inside the class but outside the method is known as an instance variable.
-   Instance variable doesn't get memory at compile time.
-   It gets memory at runtime when an object or instance is created. That is why it is known as an instance variable.

**Method in Java**

-   In Java, a method is like a function which is used to expose the behavior of an object.

**Advantage of Method**

-   Code Reusability
-   Code Optimization

## 3.1 What are the different ways to create an object in Java?

-   There are many ways to create an object in java. They are:

## 1) Anonymous object

-   Anonymous simply means nameless.
-   An object which has no reference is known as an anonymous object.
-   It can be used at the time of object creation only.
-   If you have to use an object only once, an anonymous object is a good approach.

**Example:**

*![](media/55b4318829a3f1847ecece3b5311b3d3.png)*

-   Let's see the full example of an anonymous object in Java.

*![](media/54734e6abe0e645a154d1e26f87d8e15.png)*

Output:

*![](media/0c49cb0cb8c53d737465440cfce161a2.png)*

## 2) Creating multiple objects by one type only

We can create multiple objects by one type only as we do in case of primitives.

-   Initialization of primitive variables:

*![](media/771643049e5f839c0e8f888e9c54ea2d.png)*

-   Initialization of reference variables:

*![](media/69b8eaaa8e7ad304da70e4757d043cc6.png)*

Let's see the example:

*![](media/e17d74b5d2a6951327faffd984466ef9.png)*

**Output:**

*![](media/9791bac392a5461ae1ea28cc7ea2d438.png)*

## 3.2 Ways to initialize object

There are 3 ways to initialize object in Java.

1.  By reference variable
2.  By method
3.  By constructor

## 1) Initialization object through reference variable

-   Initializing an object means storing data into the object.
-   Let's see a simple example where we are going to initialize the object through a reference variable.

**Example: TestStudent2.java**

![](media/46cec5eb22b9e49e3c8bdf89860ca7f4.png)

**Output:**

![](media/34e0a5484668acf64c27476a4973b217.png)

-   We can also create multiple objects and store information in it through reference variable.

**Example: TestStudent3.java**

![](media/66868581eda05a112cbaec40fba59f79.png)

**Output:**

![](media/cd69d1680c94296fd8d645371bde5d37.png)

## 2) Initialization object through method

-   In this example, we are creating the two objects of Student class and initializing the value to these objects by invoking the insertRecord method. Here, we are displaying the state (data) of the objects by invoking the displayInformation() method.

**Example: TestStudent4.java**

*![](media/1153e0530d05267c90cd9fb2119ccd4c.png)*

**Output:**

*![](media/0508a430e2d0651b565989e31c816f6a.png)*

-   As you can see in the above figure, object gets the memory in heap memory area.
-   The reference variable refers to the object allocated in the heap memory area.
-   Here, s1 and s2 both are reference variables that refer to the objects allocated in memory.

## 3) Initialization through a constructor

-   Let's see an example where we are maintaining records of employees.

**Example: TestEmployee.java**

*![](media/630c3367ddc5379231e9740f7d70465c.png)*

**Output:**

*![](media/9f97f893f906d26cbfa1a2c1a1c49aa5.png)*

## 4. Create a Custom Class in Java

-   Class is a templates and prototypes or blueprints from which objects are created.
-   Class does not occupy memory.
-   We can write a custom class as per our choice for an illustration purpose a sample is shown in the program below.

**Example:**

![](media/166f58267db32b8fd17f28da1c6d1a07.png)

**Output:**

![](media/3130b473a6aa16ed9317075fd82da879.png)

## 5. Java Constructors

-   In Java, a constructor is a block of codes similar to the method.
-   Constructor is called when an instance of the class is created.
-   At the time of calling constructor, memory for the object is allocated in the memory.
-   It is a special type of method which is used to initialize the object.
-   Every time an object is created using the new() keyword, at least one constructor is called.
-   It calls a default constructor if there is no constructor available in the class. In such case, Java compiler provides a default constructor by default.

## 5.1 Rules for creating Java constructor

1.  Constructor name must be the same as its class name
2.  A Constructor must have no explicit return type
3.  A Java constructor cannot be abstract, static, final, and synchronized

![](media/2926ba25034428114df422a6fab8ba67.png)

## 5.2. Types of Java constructors

-   There are two types of constructors in Java:

![](media/9db8059068645f3f9dfe8c377d625e50.png)

## 5.2.1 Java Default Constructor

-   If you don’t implement any constructor in your class, the Java compiler inserts default constructor into your code on your behalf.
-   You will not see the default constructor in your source code(the .java file) as it is inserted during compilation and present in the bytecode(.class file).

![](media/f71718f28d6da0c93780a636e7c7c8f6.png)

**Are no-arg constructor and default constructor same?**

-   The **default constructor** is inserted by compiler and has **no code** in it, on the other hand we can implement **no-arg constructor** in our class which looks like default constructor but we can provide **any initialization code** in it.

**Syntax for default constructor:**

![](media/6f28c025dbc176f03370deac4368e0e1.png)

**Example**:

-   In this example, we are creating the no-arg constructor in the Bike class.
-   It will be invoked at the time of object creation.

![](media/f523464c4843fa5c0d7c709fb57cd34a.png)

**Output:**

![](media/02b7050e152acea1e6001652b6e0caaa.png)

![](media/8719e64925f98f33661713e824e8b197.png)

-   The default constructor provides the default values to the object like 0, null, etc., depending on the type.

    **Example:**

    ![](media/e0caf131c82863155b5ab561ac0838cc.png)

    **Output:**

    **![](media/d99ad3a3430ce02ec5a756560dbb5c12.png)**

    **Explanation:**

-   In the above class, you are not creating any constructor so compiler provides you a default constructor.
-   Here 0 and null values are provided by default constructor.

## 5.2.2 Java Parameterized Constructor

-   A constructor which has a specific number of parameters is called a parameterized constructor.

**Why use the parameterized constructor?**

-   The parameterized constructor is used to provide different values to distinct objects.
-   However, you can provide the same values also.

**Example:**

-   In this example, we have created the constructor of Student class that have two parameters.
-   We can have any number of parameters in the constructor.

![](media/9d2d456fc8c8f3b32b38a2fb9bbfcb17.png)

**Output:**

![](media/801eb923495f03100e76f669e4dde5a6.png)

## 5.3. Constructor Overloading in Java

-   In Java, a constructor is just like a method but without return type. It can also be overloaded like Java methods.
-   Constructor overloading in Java is a technique of having more than one constructor with different parameter lists.
-   They are arranged in a way that each constructor performs a different task.
-   They are differentiated by the compiler by the number of parameters in the list and their types.

**Example:**

![](media/61353be56e5dac3853e690ba3639c57a.png)

**Output:**

![](media/9b7852226067766735a4f7ce59f37e40.png)

## 5.4. Difference between constructor and method in Java

![](media/bf3aeb8100376a97bb2a3f8887ee8654.png)

## 5.5. Java Copy Constructor

-   There is no copy constructor in Java. However, we can copy the values from one object to another like copy constructor in C++.
-   There are many ways to copy the values of one object into another in Java. They are:
1.  Copying values with constructor.
2.  By assigning the values of one object into another without constructor.

## 5.5.1 Copying values with constructor

-   We are going to copy the values of one object into another using Java constructor.

**Example:**

![](media/80663bcd89bde69a83cc69277dca3414.png)

**Output:**

**![](media/3853db9412690cedde8814267a03535c.png)**

## 5.5.2 Copying values without constructor

-   We can copy the values of one object into another by assigning the objects values to another object.
-   In this case, there is no need to create the constructor.

**Example:**

![](media/1027527c098028887470b0a64b676b8d.png)

**Output:**

![](media/9b7c88cdeb838165d48aee4ea00061e3.png)

## 6. Introduction of Stack and Heap in Java

-   In Java, memory management is a vital process.
-   It is managed by Java automatically.
-   The JVM divides the memory into two parts: stack memory and heap memory.
-   From the perspective of Java, both are important memory areas but both are used for different purposes.
-   The **major difference between Stack memory and heap memory** is that the stack is used to store the order of method execution and local variables while the heap memory stores the objects and it uses dynamic memory allocation and deallocation.

![](media/e600078a4d5092244eace8c9c602d343.png)

## 6.1 Stack Memory

-   The stack memory is a physical space (in RAM) allocated to each thread at run time.
-   It is created when a thread creates.
-   Memory management in the stack follows LIFO (Last-In-First-Out) order because it is accessible globally.
-   It stores the variables, references to objects, and partial results.
-   Memory allocated to stack lives until the function returns.
-   If there is no space for creating the new objects, it throws the **java.lang.StackOverFlowError.**
-   The scope of the elements is limited to their threads.

**Example of Stack Memory in Java**

![](media/f2d448af5428ec58622f7620ac193335.png)

![](media/801f4008541ac4455a363aaa5381115d.png)

**Explanation:**

1.  When the program is executed, the main method is executed first by the JVM. When the main method is called, a block is allocated for it in the call stack.
2.  The main method contains one primitive value x. This primitive value is stored in the memory block allocated for the main method.
3.  When the addOne method is called from the main method, a new block for addOne method is allocated in the stack memory.
4.  The variables specific to the method are created and stored in the allocated memory block. Upon the completion of the execution of the method, the value is returned to the calling method(here it is the main method), and the block is removed from the call stack.
5.  Similarly, when the addTwo method is called, a new block is allocated for it, and the variables are created and stored. When the method finishes execution, the value is returned to the calling method, and the block is cleared.
6.  Finally, the main method completes its execution, and the memory block corresponding to main method is cleared from the stack.

**What is StackOverflowError in Java?**

-   Stack memory is limited in size and cannot be enlarged or shrunk once created.
-   Therefore, if we use all of the stack memory, there will be no space left for upcoming method calls, and we will get the StackOverflowError.

**Example:**

![](media/31845a8e5a09a09f66b9ef05fbf1f739.png)

Error:

![](media/1309e7faa77ca2e6216ced85956fca12.png)

**Explanation:**

-   A new block on the stack is allocated for each call to the factorial method.
-   When the above program is executed, the factorial method will be called **indefinitely** because the base case is commented.
-   As the stack size is fixed, and the factorial method is called indefinitely and doesn't return any value, so the stack memory runs out, resulting in StackOverflowError.

![](media/6fed7e62ea07e02d5ada226409fa7dbc.png)

## 6.2 Heap Memory

-   It is created when the JVM starts up and used by the application as long as the application runs.
-   It stores objects and JRE classes.
-   Whenever we create objects it occupies space in the heap memory while the reference of that object creates in the stack.
-   It does not follow any order like the stack.
-   It dynamically handles the memory blocks.
-   It means, we need not to handle the memory manually.
-   For managing the memory automatically, Java provides the garbage collector that deletes the objects which are no longer being used.
-   Memory allocated to heap lives until any one event, either program terminated or memory free does not occur.
-   The elements are globally accessible in the application.
-   It is a common memory space shared with all the threads.
-   If the heap space is full, it throws the java.lang.OutOfMemoryError.

**Example of Heap Memory in Java**

![](media/06bd64bb357abd8bca9a21e5f3355fdb.png)

**Explanation:**

-   In the above example, the variable x is allocated in the stack, whereas the object list is allocated memory in the heap.
-   Only the reference to the list object is stored in the stack memory alongside x.

![](media/78b90617b11edabccb676c44fe881d2a.png)

**Why OutOfMemoryError is thrown in Java?**

-   **OutOfMemoryError** is thrown when there is no more space left in the heap to create and store a new object.
-   This happens when the Garbage Collector could not freeup any space to store new objects.

![](media/358d9716f1d81f930d72f82e81c9e402.png)

**Error**

![](media/3ecfa886f818e352301248596a60ed5a.png)

**Explanation:**

-   Consider the above program where we are repeatedly generating arrays of bigger sizes and storing values in them.
-   Once the space ran out in the heap, it threw OutOfMemoryError.

## 6.3 Difference between Stack and Heap Memory

The following table summarizes all the major differences between stack memory and heap space.

![](media/e782e0a6968fcd763693c54aeb4298df.png)

## 7. Java Garbage Collection

-   When JVM starts up, it creates a **heap area** which is known as **runtime data area.**
-   This area is used to store all the objects (instances of class).
-   Since this area is limited, it is required to manage this area efficiently by removing the objects that are no longer in use.
-   The process of removing unused objects from heap memory is known as **Garbage collection** and this is a part of memory management in Java.
-   Languages like C/C++ **don’t** support automatic garbage collection, however in java, the garbage collection is automatic.
-   In java, garbage means unreferenced objects.

## 7.1 Advantage of Garbage Collection

-   It makes java **memory efficient** because garbage collector removes the unreferenced objects from heap memory.
-   It is **automatically done** by the garbage collector(a part of JVM) so we don't need to make extra efforts.

## 7.2 How can an object be unreferenced?

![](media/5428908a18ce14fc0dc77fa78330cf75.png)

**1) By nulling a reference:**

![](media/1bfb940d7b6fc8a7821c6640e4e48d59.png)

**2) By assigning a reference to another:**

![](media/4b7e7f0f37292f4c4b107100b341752e.png)

**3) By anonymous object:**

![](media/43d99e4039f3aa5030b5fe09d450631a.png)

## finalize() method

-   The finalize() method is invoked each time before the object is garbage collected.
-   This method can be used to perform cleanup processing.
-   This method is defined in Object class as:

![](media/c8d790cbd23fcfdb9c5854b2a92dec8e.png)

![](media/89abb1ddd19c7dcb77eca48caa4453e2.png)

## gc() method

-   The gc() method is used to invoke the garbage collector to perform cleanup processing.
-   The gc() is found in System and Runtime classes.

![](media/6b9e820e9a2b831ecb0dfa695eeaa5cf.png)

![](media/9ddc3a97c17512fb9c4a188cefd097ab.png)

**Simple Example of garbage collection in java**

![](media/65bd2788eee80d6fdfca7f8aca7a3b91.png)

![](media/ef16e816da294dbd6aebaea7ce242f95.png)

![](media/71fbe5893adbb80b964d95b39eac1e7b.png)

## 8. References

1.  https://www.javatpoint.com/object-and-class-in-java
2.  https://www.geeksforgeeks.org/how-to-create-custom-class-in-java/
3.  https://www.javatpoint.com/method-in-java
4.  https://www.tutorialspoint.com/Member-variables-in-Java
5.  https://www.javatpoint.com/java-constructor
6.  https://www.javatpoint.com/stack-vs-heap-java
7.  https://www.scaler.com/topics/java/heap-memory-and-stack-memory-in-java/
8.  https://www.javatpoint.com/Garbage-Collection
9.  https://beginnersbook.com/2013/04/java-garbage-collection/
