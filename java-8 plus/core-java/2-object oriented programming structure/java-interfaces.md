# Java Interface

**Content**

1\. Interfaces

1.1 Multiple Interfaces

1.2 Difference between abstract class and interface

2\. References

## 1. Interfaces

-   Another way to achieve abstraction in Java, is with interfaces.
-   An interface is a completely "**abstract class**" that is used to group related methods with empty bodies:

**Example-1:**

![](media/802125d31ba7e832d94ac10e6e90a689.png)

-   To access the interface methods, the interface must be "implemented" by another class with the **implements** keyword (instead of extends).
-   The body of the interface method is provided by the "implement" class.

**Example-2:**

![](media/c6f2dc35dd3f0f435bed90cbf20f156b.png)

**Output:**

![](media/8b4e8761ea67d4697a1cd714f53ddaf9.png)

**Notes on Interfaces:**

-   Like **abstract classes**, interfaces **cannot** be used to create objects (in the example above, it is not possible to create an "Animal" object in the Main Class)
-   Interface methods do not have a body - the body is provided by the "implement" class
-   On implementation of an interface, you must override all of its methods
-   Interface methods are by default abstract and public
-   Interface attributes are by default public, static and final
-   An interface cannot contain a constructor (as it cannot be used to create objects)

**Why use java interfaces?**

![](media/3f590ce0f2b46ddd229ebd595f324f65.png)

**The relationship between classes and interfaces**

-   As shown in the figure given below, a class extends another class, an interface extends another interface, but a **class implements an interface**.

![](media/f2989d7eebdb0efaf14a161d591a6e03.png)

## 1.1 Multiple Interfaces

-   To implement multiple interfaces, separate them with a comma:

**Example:**

![](media/f929499b9de75dd9169aa1fb72aff44c.png)

**Output:**

![](media/06f6fb64a85980f30ae72537a8e5c1f7.png)

## 1.2 Difference between abstract class and interface

-   Abstract class and interface both are used to achieve abstraction.
-   But there are many differences between abstract class and interface that are given below.

![](media/fab3932e5f27153914697e3196b0aba5.png)

Simply, abstract class achieves partial abstraction (0 to 100%) whereas interface achieves fully abstraction (100%).

## 2. References

1.  https://www.w3schools.com/java/java_interface.asp
2.  https://www.javatpoint.com/difference-between-abstract-class-and-interface
