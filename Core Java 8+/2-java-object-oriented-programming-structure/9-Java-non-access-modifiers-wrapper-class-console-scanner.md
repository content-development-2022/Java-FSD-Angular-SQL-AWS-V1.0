# Java Non Access Modifiers

**Content**

1\. Introduction to Non-Access Modifiers in Java

1.1 Final Non Access Modifiers

1.2 Abstract Non-Access Modifier

1.3 Synchronized Non-Access Modifier

1.4 Static Non-Access Modifier

1.5 Native Non Access Modifier

1.6 Strictfp Non-Access Modifier

1.7 Transient Non-Access Modifier

2\. Wrapper Classes

2.1 Creating Wrapper Objects

3\. What is a Console?

4\. Java Scanner Class

4.1 Methods in scanner class

4.2 Advantages of scanner class

4.3 Disadvantages of scanner class

5\. References

## 1. Introduction to Non-Access Modifiers in Java

-   Non Access Modifiers are the keywords introduced in Java 7 to notify JVM about a class’s behaviour, methods or variables, etc.
-   There are 7 non-access modifiers introduced.
1.  Static
2.  Final
3.  Abstract
4.  Synchronized
5.  transient
6.  strictfp
7.  native

## 1.1 Final Non Access Modifiers

-   This modifier can be applied with:

![](media/5fd34fd7e41728eedad5c45103321855.png)

**Final Class**:

-   Final Keyword is used with a class when we want to restrict its inheritance by any other class.
-   For example, If we have a final class Honda, then any attempt to extend this class can lead to a compile-time error.

**Example:**

![](media/01f6790733eff6a163337ffa9833d1e0.png)

**Output:**

![](media/0c12b2ae3298893f5846bd856d16fd05.png)

**Final Method:**

-   Final Keyword is used to indicate Java Runtime Environment that this method is not meant to be overridden in any of its subclasses.

**Example:**

![](media/8d2f42ea5f8738fbaedbbe75359e78cc.png)

**Output:**

![](media/b65d90a3e78bf0734d750aa524d557fa.png)

**Final Variable**:

-   The final keyword is used with a variable to restrict any modification to the variable’s value, thus indicating JVM to treat it as a constant.
-   This means final variables can be initialized only **once.**

## 1.2 Abstract Non-Access Modifier

-   This modifier can be applied with:

![](media/5db762b9f531e99f74449d0287a428c5.png)

**Abstract Class**:

-   A class is declared as abstract to indicate that this class cannot be instantiated, which means no objects can be formed for this class but can be inherited.
-   Still, this class has a constructor that will be called inside the constructor of its subclass.
-   It can contain abstract as well as final methods, where abstract methods will be overridden in the subclass.

**Code:**

![](media/c5f9404aaad5fc9a42154e71b2b4a5ab.png)

**Abstract Method**

-   Abstract methods are methods without any definition.
-   It contains only the signature of the method and is meant to indicate that these need to be overridden in the subclass.

**Example:**

![](media/33c781f9983564fd2a3397ada7ad9cdb.png)

**Output:**

![](media/d1180cc8771dea1f34e9dc20949f83aa.png)

## 1.3 Synchronized Non-Access Modifier

-   This modifier can be applied with:

![](media/58e750625cf4fcc1eed1068d45f326db.png)

-   This keyword helps prevent the access of one method by multiple threads simultaneously, thus synchronizing the flow of a program and bringing out the desired results using the multithreading feature.

**Example:**

![](media/16cb0cc4e4bd680a92a0a5ee3ea63ab8.png)

**Output:**

![](media/c197fa68dce49b40e74d2d1bb28b844a.png)

## 1.4 Static Non-Access Modifier

-   This modifier can be applied with:

![](media/3c68e7a94b4f78c50cc2c0ff0810484d.png)

-   This variable is used for memory management and the first thing being referenced while loading a class.
-   These members are treated on a class level; thus, they cannot be called using an object; instead, the name of the class is used to refer to them.

**Static Variable:**

-   If a variable is declared as static, then only a single copy of the variable is created and shared among all the objects.
-   Thus any change made to the variable by one object will be reflected in other others.
-   Therefore, the variables that hold value on the class level is declared as static.

**Static Class**:

-   Static keyword can only be used with nested classes.

**Static Methods**:

-   Static Methods are referenced by class name thus can only access static member variables and other static methods.
-   Also, these methods cannot be referred to using this or super pointer.
-   The main method is the most common example of a static method that always get loaded while its class is being loaded.

**Static Block:**

-   This is said to be a block being used to perform certain operations while class is being loaded.
-   Since it is static thus can use only static members of the class.

**Example:**

![](media/41e922812bdd68e43e0c89349f65e38d.png)

**Output:**

![](media/ea9a5bc03cf02acd6f1b9d397cd4ca97.png)

## 1.5 Native Non Access Modifier

-   This modifier can be applied with:

![](media/6a1d9e3c82879134b3508618fe28e660.png)

-   The native keyword is used only with the methods to indicate that the particular method is written in platform-dependent.
-   These are used to improve the system’s performance, and the existing legacy code can be easily reused.

![](media/44190248fd271d6699491eecd7559a00.png)

**Example:** Consider a function myfun1 in class NativeDemo that is written in C++. To use this code, we will create a link library mylib1 and load it using the classnstatic block.

![](media/42c7ec813bdacce3e36ebb126930e40a.png)

## 1.6 Strictfp Non-Access Modifier

**Strictfp Class / Method:**

-   This keyword is used to ensure that results from an operation on floating-point numbers brings out the same results on every platform.
-   This keyword cannot be used with abstract methods, variables or constructors as these need not contain operations.

**Example:**

![](media/3f3b6bcb7adde8674d4996b12d440999.png)

**Output:**

![](media/9afe7d0b2669518bd5467a1e3fc9edc8.png)

## 1.7 Transient Non-Access Modifier

-   While transferring the data from one end to another over a network, it must be serialised for successful receiving of data, which means convert to byte stream before sending and converting it back at receiving end.
-   To tell JVM about the members who need not undergo serialization instead of being lost during transfer, a transient modifier comes into the picture.

**Syntax**:

![](media/339b398a85cbcb1bfca0c03f43c5e45b.png)

**Example:**

![](media/a16096b2800c431ebf78e32d3e9a280c.png)

**Output:**

![](media/31aad6686abc565fa215a7b20111e5a7.png)

## 2. Wrapper Classes

-   The eight primitive data types byte, short, int, long, float, double, char and boolean are not objects, **Wrapper classes are used for converting primitive data types into objects.**
-   The table below shows the primitive type and the equivalent wrapper class:

![](media/4b45b88dd3e7f552e63814a6b8f7e1cf.png)

-   Sometimes you must use wrapper classes, for example when working with Collection objects, such as ArrayList, where primitive types cannot be used (the list can only store objects):

**Example**

![](media/d7b3d68bed63fe327d75e1052b7e8481.png)

## 2.1 Creating Wrapper Objects

-   To create a wrapper object, use the wrapper class instead of the primitive type.
-   To get the value, you can just print the object:

**Example-1:**

![](media/0dfec0df31729bb85615e52ec5ecd8ef.png)

**Output:**

![](media/28039c0a06538e2e23e19790e385d6e7.png)

-   Since you're now working with objects, you can use certain methods to get information about the specific object.
-   For example, the following methods are used to get the value associated with the corresponding wrapper object: intValue(), byteValue(), shortValue(), longValue(), floatValue(), doubleValue(), charValue(), booleanValue().
-   This example will output the same result as the example above:

**Example-2:**

![](media/f958aa3c4fd57b4c5d5543b2ea2b9a21.png)

**Output:**

![](media/28c17da75dc7c152a810feb9e3fc2fe6.png)

-   Another useful method is the **toString()** method, which is used to convert wrapper objects to strings.
-   In the following example, we convert an Integer to a String, and use the length() method of the String class to output the length of the "string".

**Example-3:**

![](media/dcb49015edc0124df20371662266d02a.png)

**Output:**

![](media/a45688217e7111c263c0b3780f4256ca.png)

## 3. What is a Console?

-   To run a program, we might need input from the programmer or user according to the requirement.
-   We cannot always take input just from the program. Sometimes, we can take the input from the console or terminal too.
-   The process of taking input from the console is introduced by the concept of Java Console.
-   Java programming language provides three ways in order to take input from the console and provide its corresponding output on the same console.
1.  Using Java Scanner class (Basic level)
2.  Using Java BufferedReader class (Intermediate level)
3.  Using Java Console class

**Note:** In this document we only discuss the scanner class.

## 4. Java Scanner Class

-   Java **Scanner class** allows the user to take input from the console.
-   It belongs to **java.util** package.
-   It is used to read the input of primitive types like int, double, long, short, float, and byte.
-   It is the easiest way to read input in Java program.

**Syntax**

![](media/b23e3d06dd2a804eeb1e26b02886d1d0.png)

-   Here, " Scanner " is considered as a class and " sc " is an object that is created within a class.
-   So, in order to scan any input in the entire program, we can use this object that is created in the " Scanner " class.
-   The above statement creates a constructor of the Scanner class having **System.in** as an argument.
-   It means it is going to read from the standard input stream of the program.
-   The **java.util** package should be import while using Scanner class.

## 4.1 Methods in scanner class

-   There are different methods used for scanning different data types.
-   The type of method that we consider depends on the data type of the input that we want to take.
-   There are eight methods in the Scanner class, as there are eight general Primitive data types.

![](media/65d2b7a47a56f1b0e105f11c9551ae4c.png)

**Example-1: Integer input from user**

-   The following example allows user to read an integer form the System.in.

![](media/cac7bdbe5f4c1f818d6fa23a0c8c9278.png)

**Output:**

![](media/ab9ad1b068c9918d3772cb02cebdcabb.png)

**Example-2: String input from user**

-   Let's see another example, in which we have taken string input.

![](media/99c402913c1cb773222eba5eed958293.png)

**Output:**

![](media/e8bac996fc4855dc39e193f584ba4053.png)

## 4.2 Advantages of scanner class

-   This class provides several methods according to the data type used and that match the user's requirement.
-   It is the basic class used to scan an input that runs on almost all versions of Java.

## 4.3 Disadvantages of scanner class

-   It runs and executes a little slower as the data must be parsed before being executed.
-   The methods that are part of the class " Scanner " are not synchronized.

## 5. References

1.  https://www.educba.com/non-access-modifiers-in-java/
2.  https://www.w3schools.com/java/java_wrapper_classes.asp
3.  https://www.javatpoint.com/how-to-get-input-from-user-in-java
4.  https://www.javatpoint.com/console-in-java
