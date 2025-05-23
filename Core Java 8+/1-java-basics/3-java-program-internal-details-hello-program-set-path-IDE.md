# Program Internal Details, Hello Java Program, Set Path

**Content**

[1. Internal Details of Program](#1-internal-details-of-program)

[1.1 What happens at compile time?](#11-what-happens-at-compile-time)

[1.2 What happens at run time?](#12-what-happens-at-run-time)

[2. First Java Program \| Hello Java Example](#2-first-java-program--hello-java-example)

[2.1 The requirement for Hello Java Example](#21-the-requirements-for-hello-java-example)

[2.2 Creating Hello java Example](#22-creating-hello-java-example)

[2.3 Keywords used in Hello Java Program](#23-keywords-used-in-hello-java-program)

[2.4 In how many ways we can write a Java program?](#24-in-how-many-ways-we-can-write-a-java-program)

[3. How to set path in Java](#3-how-to-set-path-in-java)

[3.1 How to set the Temporary Path of JDK in Windows](#31-how-to-set-the-temporary-path-of-jdk-in-windows)

[3.2 How to set the Permanent Path of JDK in Windows](#32-how-to-set-the-permanent-path-of-jdk-in-windows)

[4. Intergrated Development Environment (IDE)](#4-intergrated-development-environment-ide)

[5. References](#5-references)

# 1. Internal Details of Program

Let's see what happens while we compile and run the Java program.

## 1.1 What happens at compile time?

-   At compile time, the Java file is compiled by Java Compiler (It does not interact with OS) and is converted into bytecode.

![](media/compile-time.png)

## 1.2 What happens at run time?

-   At runtime, the following steps are performed:

![](media/run-time.png)

**Classloader:**

-   It is a subsystem of JVM that is used to load class files.

**Bytecode Verifier:**

-   Checks the code fragments for illegal code that can violate access rights to objects.

**Interpreter:**

-   Reads bytecode stream and then executes the instructions.

# 2. First Java Program \| Hello Java Example

-   Here we will see how to write a simple program in Java.

## 2.1 The requirements for Hello Java Example

For executing any Java program, the following software or application must be properly installed.

-   Install Java (JDK) by downloading it. Any version of Java 8 or above 8 is good. Java can be installed from this link - https://www.oracle.com/java/technologies/downloads/
-   Set path of the jdk/bin directory.
-   Create the Java program
-   Compile and run the Java program

## 2.2 Creating Hello java Example

-   To write a simple program, you need to open notepad by clicking on **start menu -\> All Programs -\> Accessories -\> Notepad** and type a simple program as shown below:

![](media/notepad-1.png)

-   Save the file with **classname.java**

    **Example:** Simple.java

-   In order to compile and run the above program, you need to open the command prompt by clicking on **start menu -\> All Programs -\> Accessories -\> command prompt**.

![](media/cmd-1.png)

-   To compile and run the above program, go to the directory where the file is saved; my current directory is c:\\new.

Type the following commands here:

-   **To compile:** javac Simple.java
-   **To execute:** java Simple

**Output:**

![](media/cmd-2.png)

## 2.3 Keywords used in Hello Java Program

-   Let's try to understand the meaning of class, public, static, void, main, String[], System.out.println() used in the program.

**class**

-   It is a keyword.
-   It is used to declare a class in Java.

**public**

-   It is a keyword.
-   It is an access modifier that represents visibility.
-   It means it is visible to all.

**static**

-   It is a keyword.
-   If we declare any method as static, it is known as the static method.
-   The core advantage of the static method is that there is no need to create an object to invoke the static method.
-   The main() method is executed by the JVM, so it doesn't require creating an object to invoke the main() method. So, it saves memory.

**void**

-   It is the return type of the method.
-   It means it doesn't return any value.

**main**

-   It represents the starting point of the program.
-   It is a pre-defined name.

**String[] args** or **String args[]**

-   It is used to work with command line argument

**System.out.println()**

-   It is a print statement used to print an output on the console.
-   Here, System is a class, out is an object of the PrintStream class, println() is a method of the PrintStream class.

## 2.4 In how many ways we can write a Java program?

-   There are many ways to write a Java program.
-   The modifications that can be done in a Java program are given below:

### 2.4.1 By changing the sequence of the modifiers, method prototype is not changed in Java.

```java
static public void main(String args[])
```

### 2.4.2 The subscript notation in the Java array can be used after type, before the variable or after the variable.

```java
static public void main(String[] args)
static public void main(String [] args)
static public void main(String args[])
```

### 2.4.3 You can provide var-args support to the main() method by passing 3 ellipses (dots)

```java
static public void main(String… args)
```

### 2.4.4 Having a semicolon at the end of class is optional in Java.

```java
class A{  
static public void main(String... args){  
System.out.println("hello java4");  
}  
};  
```

### 2.4.5 Valid Java main() method signature

```java
public static void main(String[] args)  
public static void main(String []args)  
public static void main(String args[])  
public static void main(String... args)  
static public void main(String[] args)  
public static final void main(String[] args)  
final public static void main(String[] args)  
final strictfp public static void main(String[] args)  
```

### 2.4.6 Invalid Java main() method signature

```java
public void main(String[] args)  
static void main(String[] args)  
public void static main(String[] args)  
abstract public static void main(String[] args)  
```

### Resolving an error "javac is not recognized as an internal or external command"?

-   If there occurs an error **"javac is not recognized as an internal or external command"** you need to set a path.
-   Here DOS/command prompt doesn't recognize javac and java as internal or external command.
-   To overcome this problem, we need to set a path.

# 3. How to set path in Java

-   The path is required to be set for using tools such as javac, java, etc.
-   If you are saving the Java source file inside the JDK/bin directory, the path is not required to be set because all the tools will be available in the current directory. This is highly not recommended as we do not want to disturb the Java software installed in our computer.
-   However, if you have your Java file anywhere outside the JDK/bin folder, it is necessary to set the path of JDK.
-   There are two ways to set the path in Java:
    -   Temporary
    -   Permanent

## 3.1 How to set the Temporary Path of JDK in Windows

To set the temporary path of JDK, you need to follow the following steps:

-   Open the command prompt
-   Copy the path of the JDK/bin directory
-   Write in command prompt:
    -   **set path=copied_path;**
    -   **set path=%path%;copied_path;**
        -   **%path% appends the existing path**

**Example**

```
set path=C:\Program Files\Java\jdk-14.0.2\bin;
```

-   Let's see it in the figure given below:

![](media/cmd-3.png)

## 3.2 How to set the Permanent Path of JDK in Windows

For setting the path to JDK permanently, you need to follow these steps:

-   Go to **MyComputer -\> properties -\> advances system settings -\> advanced tab -\> environment variables -\> new tab of user variable -\>** write path in **variable name -\>** write path of bin folder in **variable value -\> ok -\> ok -\> ok**

**Example**

**Step 1:** Go to MyComputer and right click on mycomputer. Click on properties.

![](media/path-1.png)

**Step 2:** Click on the **advanced system settings.**

![](media/path-2.png)

**Step 3:** Click on the **advanced tab.**

![](media/path-3.png)

**Step 4:** Click on **environment variables.**

![](media/path-4.png)

**Step 5:** Click on the **new** button of **user variables.**

![](media/path-5.png)

**Step 6:** Write the **path** in the **variable name.**

![](media/path-6.png)

**Step 7:** Copy the path of **bin folder.**

![](media/path-7.png)

**Step 8:** Paste **path of bin folder** in the **variable value.**

![](media/path-8.png)

**Step 9:** Click on **ok** button.

![](media/path-9.png)

**Step 10:** Click on **ok** button.

![](media/path-10.png)

**Step 11:** Click on **ok** button.

![](media/path-11.png)

-   Now your permanent path is set.
-   You can now execute any program of java from any drive/folder/location.

# 4. Intergrated Development Environment (IDE)

-   **An IDE, or Integrated Development Environment, is a program which helps you write software.**
-   **An IDE helps you organise your software projects, write code, and then test and debug it.**
-   **Popular IDEs include Eclipse, IntelliJ and Microsoft Visual Studio.**

An IDE usually includes features which help you to:

-   Write code
-   Compile or package code
-   Debug your application

Can an IDE do other things?

-   Sure! And many of them do.
-   Some IDEs add features for running tests, writing documentation, and even creating diagrams.
-   But coding, compiling and debugging are three core features of any decent IDE.

**Do you need an IDE to write Java code?**

-   No, you don’t need to write Java code in an IDE. You can use any text editor you like, and then compile the code with javac.
-   You could be writing code for the Mars rover, nuclear power stations, or even financial trading algorithms, with trusty Windows Notepad, and javac (the Java compiler command).
-   If you’re just starting to learn Java, use a text editor first
-   But why? If an IDE can do all of the work for you, why start out creating programs by hand?
-   **Coding by hand helps you see the basics of the language, and it will give you way more confidence in future, if you have to troubleshoot a problem.**
-   If you are completely reliant on an IDE, and you have no knowledge of what the IDE is doing for you, you will find it harder in future to solve problems.
-   An IDE is useful once you’re past the beginner stage
-   An IDE helps you organise your projects, run tests, compile the code, format it correctly, and much more.

**The most popular Java IDEs**

Some of the top Java IDEs in use today are:

-   IntelliJ IDEA
-   Eclipse
-   NetBeans
-   Oracle JDeveloper
-   Visual Studio Code (with the Java Extension Pack installed)

# 5. References

1.  <https://www.javatpoint.com/internal-details-of-hello-java-program>
2.  https://www.javatpoint.com/simple-program-of-java
3.  <https://www.javatpoint.com/how-to-set-path-in-java>
4.  https://www.tutorialworks.com/java-ide/
