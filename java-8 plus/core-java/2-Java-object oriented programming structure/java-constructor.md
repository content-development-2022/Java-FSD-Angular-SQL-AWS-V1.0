# Java Constructors

**Content**

1\. Java Constructors

1.1 Rules for creating Java constructor

2\. Types of Java constructors

2.1 Java Default Constructor

2.2 Java Parameterized Constructor

3\. Constructor Overloading in Java

4\. Difference between constructor and method in Java

5\. Java Copy Constructor

5.1 Copying values with constructor

5.2 Copying values without constructor

6\. References

## 1. Java Constructors

-   In Java, a constructor is a block of codes similar to the method.
-   Constructor is called when an instance of the class is created.
-   At the time of calling constructor, memory for the object is allocated in the memory.
-   It is a special type of method which is used to initialize the object.
-   Every time an object is created using the new() keyword, at least one constructor is called.
-   It calls a default constructor if there is no constructor available in the class. In such case, Java compiler provides a default constructor by default.

## 1.1 Rules for creating Java constructor

1.  Constructor name must be the same as its class name
2.  A Constructor must have no explicit return type
3.  A Java constructor cannot be abstract, static, final, and synchronized

![](media/2926ba25034428114df422a6fab8ba67.png)

## 2. Types of Java constructors

-   There are two types of constructors in Java:

![](media/9db8059068645f3f9dfe8c377d625e50.png)

## 2.1 Java Default Constructor

-   A constructor is called "Default Constructor" when it doesn't have any parameter.

**Syntax:**

![](media/6f28c025dbc176f03370deac4368e0e1.png)

**Example**:

-   In this example, we are creating the no-arg constructor in the Bike class.
-   It will be invoked at the time of object creation.

![](media/f523464c4843fa5c0d7c709fb57cd34a.png)

**Output:**

![](media/02b7050e152acea1e6001652b6e0caaa.png)

![](media/8719e64925f98f33661713e824e8b197.png)

![](media/971b7475fc347b2867559f830b71d4ed.png)

**Q) What is the purpose of a default constructor?**

-   The default constructor is used to provide the default values to the object like 0, null, etc., depending on the type.

**Example of default constructor that displays the default values**

![](media/b3cfdce0ed464f6de5ee315eb2550178.png)

**Output:**

![](media/93d675304c1306aefb61d506beda52d0.png)

**Explanation:**

-   In the above class, you are not creating any constructor so compiler provides you a default constructor.
-   Here 0 and null values are provided by default constructor.

## 2.2 Java Parameterized Constructor

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

## 3. Constructor Overloading in Java

-   In Java, a constructor is just like a method but without return type. It can also be overloaded like Java methods.
-   Constructor overloading in Java is a technique of having more than one constructor with different parameter lists.
-   They are arranged in a way that each constructor performs a different task.
-   They are differentiated by the compiler by the number of parameters in the list and their types.

**Example:**

![](media/61353be56e5dac3853e690ba3639c57a.png)

**Output:**

![](media/9b7852226067766735a4f7ce59f37e40.png)

## 4. Difference between constructor and method in Java

![](media/bf3aeb8100376a97bb2a3f8887ee8654.png)

## 5. Java Copy Constructor

-   There is no copy constructor in Java. However, we can copy the values from one object to another like copy constructor in C++.
-   There are many ways to copy the values of one object into another in Java. They are:
1.  Copying values with constructor.
2.  By assigning the values of one object into another without constructor.

## 5.1 Copying values with constructor

-   We are going to copy the values of one object into another using Java constructor.

**Example:**

![](media/80663bcd89bde69a83cc69277dca3414.png)

**Output:**

**![](media/3853db9412690cedde8814267a03535c.png)**

## 5.2 Copying values without constructor

-   We can copy the values of one object into another by assigning the objects values to another object.
-   In this case, there is no need to create the constructor.

**Example:**

![](media/1027527c098028887470b0a64b676b8d.png)

**Output:**

![](media/9b7c88cdeb838165d48aee4ea00061e3.png)

## 6. References

1.  https://www.javatpoint.com/java-constructor
