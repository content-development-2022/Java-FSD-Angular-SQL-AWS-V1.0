# Java Reading From the Console (Scanner Class)

**Content**

1\. What is a Console?

2\. Java Scanner Class

2.1 Methods in scanner class

2.2 Advantages of scanner class

2.3 Disadvantages of scanner class

3\. References

## 1. What is a Console?

-   To run a program, we might need input from the programmer or user according to the requirement.
-   We cannot always take input just from the program. Sometimes, we can take the input from the console or terminal too.
-   The process of taking input from the console is introduced by the concept of Java Console.
-   Java programming language provides three ways in order to take input from the console and provide its corresponding output on the same console.
1.  Using Java Scanner class (Basic level)
2.  Using Java BufferedReader class (Intermediate level)
3.  Using Java Console class

**Note:** In this document we only discuss the scanner class.

## 2. Java Scanner Class

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

## 2.1 Methods in scanner class

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

## 2.2 Advantages of scanner class

-   This class provides several methods according to the data type used and that match the user's requirement.
-   It is the basic class used to scan an input that runs on almost all versions of Java.

## 2.3 Disadvantages of scanner class

-   It runs and executes a little slower as the data must be parsed before being executed.
-   The methods that are part of the class " Scanner " are not synchronized.

## 3. References

1.  https://www.javatpoint.com/how-to-get-input-from-user-in-java
2.  https://www.javatpoint.com/console-in-java
