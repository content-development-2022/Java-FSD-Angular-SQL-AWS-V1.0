# Java Comments

**Content**

1\. Java Comments

1.1 Why do we use comments in a code?

2\. Types of Java Comments

2.1 Single Line Comment

2.2 Multi Line Comment

2.3 Documentation Comment

3\. Are Java comments executable?

4\. References

## 1. Java Comments

-   The Java comments are the statements in a program that are not executed by the compiler and interpreter.

## 1.1 Why do we use comments in a code?

-   Comments are used to make the program more readable by adding the details of the code.
-   It makes easy to maintain the code and to find the errors easily.
-   The comments can be used to provide information or explanation about the variable, method, class, or any statement.
-   It can also be used to prevent the execution of program code while testing the alternative code.

## 2. Types of Java Comments

**There are three types of comments in Java.**

![](media/5da2cd019b0110b2f023e6fa02ec6aec.png)

## 2.1 Single Line Comment

-   The single-line comment is used to comment only one line of the code.
-   It is the widely used and easiest way of commenting the statements.
-   Single line comments starts with two forward slashes **(//)**.
-   Any text in front of // is not executed by Java.

**Syntax:**

![](media/2ca9616ac66b9ccc1126033d0b6d1a49.png)

**Example:**

![](media/dcc483ba72a87168ced5b3ee9ce1a599.png)

**Output:**

![](media/ad5c76f06accdf9b254bc89c3d7901e0.png)

## 2.2 Multi Line Comment

-   The multi-line comment is used to comment multiple lines of code.
-   It can be used to explain a complex code snippet or to comment multiple lines of code at a time (as it will be difficult to use single-line comments there).
-   Multi-line comments are placed between /\* and \*/. Any text between /\* and \*/ is not executed by Java.

**Syntax:**

![](media/4af96d642abbdd1b40376d380810be59.png)

**Example:**

![](media/6928827aab50e42d1920eefdc87d5f68.png)

**Output:**

![](media/f0ed258cc55a271eb96444724a89e174.png)

![](media/bed6cee1cc717f0d94efb927d45b50c2.png)

## 2.3 Documentation Comment

-   Documentation comments are usually used to write large programs for a project or software application as it helps to create documentation API.
-   These APIs are needed for reference, i.e., which classes, methods, arguments, etc., are used in the code.
-   To create documentation API, we need to use the **javadoc tool**.
-   The documentation comments are placed between /\*\* and \*/.

**Syntax:**

![](media/c0ab8c43b17e6db0a8e57f0ce2fc46ff.png)

**Example:**

![](media/9aa7520cd77e94bef5e7542bcdc66e98.png)

**Output:**

![](media/30452d1e75aec4b79542300de1a0c416.png)

-   Create documentation API by **javadoc** tool:

![](media/7afcc5ab058dd7564a06a9620c478f34.png)

-   Now, the HTML files are created for the **Calculate** class in the current directory, i.e., **abcDemo**.
-   Open the HTML files, and we can see the explanation of Calculate class provided through the documentation comment.

## 3. Are Java comments executable?

-   Java comments are not executed by the compiler or interpreter, however, before the lexical transformation of code in compiler, contents of the code are encoded into ASCII in order to make the processing easy.

## 4. References

1.  https://www.javatpoint.com/java-comments
