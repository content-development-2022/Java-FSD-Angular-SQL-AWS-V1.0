# Encapsulation in Java

**Content**

## 1. What is encapsulation?

-   The whole idea behind encapsulation is to hide the implementation details from users. If a data member is private it means it can only be accessed within the same class. No outside class can access private data member (variable) of other class.
-   However if we setup public getter and setter methods to update (for example void setSSN(int ssn))and read (for example int getSSN()) the private data fields then the outside class can access those private data fields via public methods.
-   This way data can only be accessed by public methods thus making the private fields and their implementation hidden for outside classes. That’s why encapsulation is known as **data hiding.** Lets see an example to understand this concept better.

## Example of Encapsulation in Java

How to implement encapsulation in java:

1.  Make the instance variables private so that they cannot be accessed directly from outside the class. You can only set and get values of these variables through the methods of the class.
2.  Have getter and setter methods in the class to set and get the values of the fields.

![](media/a0cc5324a7660f7deefb495cda1fd418.png)

**Output:**

![](media/48743ac15477a927d30bae18444405bd.png)

In above example all the three data members (or data fields) are private(see: [Access Modifiers in Java](https://beginnersbook.com/2013/05/java-access-modifiers/)) which cannot be accessed directly. These fields can be accessed via public methods only. Fields empName, ssn and empAge are made hidden data fields using encapsulation technique of OOPs.

### Advantage of Encapsulation in Java

By providing only a setter or getter method, you can make the class **read-only or write-only**. In other words, you can skip the getter or setter methods.

It provides you the **control over the data**. Suppose you want to set the value of id which should be greater than 100 only, you can write the logic inside the setter method. You can write the logic not to store the negative numbers in the setter methods.

It is a way to achieve **data hiding** in Java because other class will not be able to access the data through the private data members.

The encapsulate class is **easy to test**. So, it is better for unit testing.

The standard IDE's are providing the facility to generate the getters and setters. So, it is **easy and fast to create an encapsulated class** in Java.

References

https://www.javatpoint.com/encapsulation

https://beginnersbook.com/2013/05/encapsulation-in-java/
