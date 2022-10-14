# Java Object Casting

**Content**

1\. Object Typecasting

1.1 Upcasting

1.2 Downcasting

1.3 Why we need Upcasting and Downcasting?

1.4 Difference between Upcasting and Downcasting

2\. References

## 1. Object Typecasting

-   A process of converting one data type to another is known as **Typecasting**.
-   In Java, the object can also be typecasted like the datatypes.
-   Parent and Child objects are two types of objects.
-   So, there are two types of typecasting possible for an object, i.e., **Parent to Child** and **Child to Parent** or can say **Upcasting** and **Downcasting**.
-   Typecasting is used to ensure whether variables are correctly processed by a function or not.
-   In Upcasting and Downcasting, we typecast a child object to a parent object and a parent object to a child object simultaneously.
-   We can perform Upcasting implicitly or explicitly, but downcasting cannot be implicitly possible.

![](media/0371286d114702bc45c08c71350d85c7.png)

## 1.1 Upcasting

-   Upcasting is a type of object typecasting in which a **child object** is typecasted to a **parent class object**.
-   By using the Upcasting, we can easily access the variables and methods of the parent class to the child class.
-   Here, we don't access all the variables and the method.
-   We access only some specified variables and methods of the child class.
-   Upcasting is also known as **Generalization** and **Widening**.

**Example:**

![](media/c30f1d068789794092e8c3398c809d69.png)

**Output:**

![](media/520190185ce12afce2df4788177c3820.png)

## 1.2 Downcasting

-   **Downcasting** is another type of object typecasting.
-   In Downcasting, we assign a parent class reference object to the child class.
-   In Java, we cannot assign a parent class reference object to the child class, but if we perform downcasting, we will not get any compile-time error.
-   However, when we run it, it throws the **"ClassCastException"**.
-   Now the point is if downcasting is not possible in Java, then why is it allowed by the compiler? In Java, some scenarios allow us to perform downcasting.
-   Below is an example of downcasting in which both the valid and the invalid scenarios are explained:

**Example:**

![](media/27bbee68f45efa4010939141e1b582a4.png)

**Output:**

## ![](media/7e2482b6f6413b0c698f154633da19b3.png)

## 1.3 Why we need Upcasting and Downcasting?

-   In Java, we rarely use **Upcasting**. We use it when we need to develop a code that deals with only the parent class.
-   **Downcasting** is used when we need to develop a code that accesses behaviors of the child class.

![](media/c44708b1be9ed561fe3a4340298c1a4b.png)

## 1.4 Difference between Upcasting and Downcasting

-   These are the following differences between Upcasting and Downcasting:

![](media/a43441aed780c36e90ad48c3beb8815a.png)

## 2. References

1.  https://www.javatpoint.com/upcasting-and-downcasting-in-java
