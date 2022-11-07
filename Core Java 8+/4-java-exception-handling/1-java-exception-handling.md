## Introduction

An *exception* is an error event that can happen during the execution of a program and disrupts its normal flow. Java provides a robust and object-oriented way to handle exception scenarios known as Java Exception Handling.

Exceptions in Java can arise from different kinds of situations such as wrong data entered by the user, hardware failure, network connection failure, or a database server that is down. The code that specifies what to do in specific exception scenarios is called exception handling.

## Throwing and Catching Exceptions

Java creates an *exception object* when an error occurs while executing a statement. The exception object contains a lot of debugging information such as method hierarchy, line number where the exception occurred, and type of exception.

If an exception occurs in a method, the process of creating the exception object and handing it over to the runtime environment is called *“throwing the exception”*. The normal flow of the program halts and the [Java Runtime Environment (JRE)](https://www.digitalocean.com/community/tutorials/difference-jdk-vs-jre-vs-jvm) tries to find the handler for the exception. Exception Handler is the block of code that can process the exception object.

-   The logic to find the exception handler begins with searching in the method where the error occurred.
-   If no appropriate handler is found, then it will move to the caller method.
-   And so on.

So if the method’s call stack is A-\>B-\>C and an exception is raised in method C, then the search for the appropriate handler will move from C-\>B-\>A.

If an appropriate exception handler is found, the exception object is passed to the handler to process it. The handler is said to be *“catching the exception”*. If there is no appropriate exception handler, found then the program terminates and prints information about the exception to the console.

Java Exception handling framework is used to handle runtime errors only. The compile-time errors have to be fixed by the developer writing the code else the program won’t execute.

## Java Exception Handling Keywords

Java provides specific keywords for exception handling purposes.

1.  **throw** – We know that if an error occurs, an exception object is getting created and then Java runtime starts processing to handle them. Sometimes we might want to generate exceptions explicitly in our code. For example, in a user authentication program, we should throw exceptions to clients if the password is null. The throw keyword is used to throw exceptions to the runtime to handle it.
2.  **throws** – When we are throwing an exception in a method and not handling it, then we have to use the throws keyword in the method signature to let the caller program know the exceptions that might be thrown by the method. The caller method might handle these exceptions or propagate them to its caller method using the throws keyword. We can provide multiple exceptions in the throws clause, and it can be used with the main() method also.
3.  **try-catch** – We use the try-catch block for exception handling in our code. try is the start of the block and catch is at the end of the try block to handle the exceptions. We can have multiple catch blocks with a try block. The try-catch block can be nested too. The catch block requires a parameter that should be of type Exception.
4.  **finally** – the finally block is optional and can be used only with a try-catch block. Since exception halts the process of execution, we might have some resources open that will not get closed, so we can use the finally block. The finally block always gets executed, whether an exception occurred or not.

**An Exception Handling Example**

```java
package com.journaldev.exceptions;
import java.io.FileNotFoundException;
import java.io.IOException;
public class ExceptionHandling {
public static void main(String[] args) throws FileNotFoundException, IOException {
try {
testException(-5);
testException(-10);
} catch(FileNotFoundException e) {
e.printStackTrace();
} catch(IOException e) {
e.printStackTrace();
} finally {
System.out.println("Releasing resources");
}
testException(15);
}
public static void testException(int i) throws FileNotFoundException, IOException {
if (i < 0) {
FileNotFoundException myException = new FileNotFoundException("Negative Integer " + i);
throw myException;
} else if (i > 10) {
throw new IOException("Only supported for index 0 to 10");
}
}
}
```

-   The testException() method is throwing exceptions using the throw keyword. The method signature uses the throws keyword to let the caller know the type of exceptions it might throw.
-   In the main() method, I am handling exceptions using the try-catch block in the main() method. When I am not handling it, I am propagating it to runtime with the throws clause in the main() method.
-   The testException(-10) never gets executed because of the exception and then the finally block is executed.

The printStackTrace() is one of the useful methods in the Exception class for debugging purposes.

This code will output the following:

```
Output
java.io.FileNotFoundException: Negative Integer -5
	at com.journaldev.exceptions.ExceptionHandling.testException(ExceptionHandling.java:24)
	at com.journaldev.exceptions.ExceptionHandling.main(ExceptionHandling.java:10)
Releasing resources
Exception in thread "main" java.io.IOException: Only supported for index 0 to 10
	at com.journaldev.exceptions.ExceptionHandling.testException(ExceptionHandling.java:27)
	at com.journaldev.exceptions.ExceptionHandling.main(ExceptionHandling.java:19)
```

Some important points to note:

-   We can’t have catch or finally clause without a try statement.
-   A try statement should have either catch block or finally block, it can have both blocks.
-   We can’t write any code between try-catch-finally blocks.
-   We can have multiple catch blocks with a single try statement.
-   try-catch blocks can be nested similar to if-else statements.
-   We can have only one finally block with a try-catch statement.

## Java Exception Hierarchy

As stated earlier, when an exception is raised an exception object is getting created. Java Exceptions are hierarchical and inheritance is used to categorize different types of exceptions. Throwable is the parent class of Java Exceptions Hierarchy and it has two child objects – Error and Exception. Exceptions are further divided into Checked Exceptions and Runtime Exceptions.

1.  **Errors**: Errors are exceptional scenarios that are out of the scope of application, and it’s not possible to anticipate and recover from them. For example, hardware failure, Java virtual machine (JVM) crash, or out-of-memory error. That’s why we have a separate hierarchy of Errors and we should not try to handle these situations. Some of the common Errors are OutOfMemoryError and StackOverflowError.
2.  **Checked Exceptions**: Checked Exceptions are exceptional scenarios that we can anticipate in a program and try to recover from it. For example, FileNotFoundException. We should catch this exception and provide a useful message to the user and log it properly for debugging purposes. The Exception is the parent class of all Checked Exceptions. If we are throwing a Checked Exception, we must catch it in the same method, or we have to propagate it to the caller using the throws keyword.
3.  **Runtime Exception**: Runtime Exceptions are caused by bad programming. For example, trying to retrieve an element from an array. We should check the length of the array first before trying to retrieve the element otherwise it might throw ArrayIndexOutOfBoundException at runtime. RuntimeException is the parent class of all Runtime Exceptions. If we are throwing any Runtime Exception in a method, it’s not required to specify them in the method signature throws clause. Runtime exceptions can be avoided with better programming.

![Diagram of the Java Exception Hierarchy. Throwable is at the top of the diagram. One branch of this tree is Error. Below Error are OutOfMemoryError and IOError. Another branch of this tree is Exception. Exception splits into IOException and RuntimeException. Below IOException is FileNotFoundException. Below RuntimeException is NullPointerException.](media/f91bff1cfe1837da890fc91eaaa51846.png)

**Some useful methods of Exception Classes**

Java Exception and all of its subclasses don’t provide any specific methods, and all of the methods are defined in the base class - Throwable. The Exception classes are created to specify different kinds of Exception scenarios so that we can easily identify the root cause and handle the Exception according to its type. The Throwable class implements the Serializable interface for interoperability.

Some of the useful methods of the Throwable class are:

1.  **public String getMessage()** – This method returns the message String of Throwable and the message can be provided while creating the exception through its constructor.
2.  **public String getLocalizedMessage()** – This method is provided so that subclasses can override it to provide a locale-specific message to the calling program. The Throwable class implementation of this method uses the getMessage() method to return the exception message.
3.  **public synchronized Throwable getCause()** – This method returns the cause of the exception or null if the cause is unknown.
4.  **public String toString()** – This method returns the information about Throwable in String format, the returned String contains the name of the Throwable class and localized message.
5.  **public void printStackTrace()** – This method prints the stack trace information to the standard error stream, this method is overloaded, and we can pass PrintStream or PrintWriter as an argument to write the stack trace information to the file or stream.

**Java 7 Automatic Resource Management and Catch block improvements**

If you are catching a lot of exceptions in a single try block, you will notice that the catch block code mostly consists of redundant code to log the error. In Java 7, one of the features was an improved catch block where we can catch multiple exceptions in a single catch block. Here is an example of the catch block with this feature:

```java
catch (IOException | SQLException ex) {
logger.error(ex);
throw new MyException(ex.getMessage());
}
```

There are some constraints such as the exception object is final and we can’t modify it inside the catch block, read the full analysis at [Java 7 Catch Block Improvements](https://www.digitalocean.com/community/tutorials/java-catch-multiple-exceptions-rethrow-exception).

Most of the time, we use the finally block just to close the resources. Sometimes we forget to close them and get runtime exceptions when the resources are exhausted. These exceptions are hard to debug, and we might need to look into each place where we are using that resource to make sure we are closing it. In Java 7, one of the improvements was try-with-resources where we can create a resource in the try statement itself and use it inside the try-catch block. When the execution comes out of the try-catch block, the runtime environment automatically closes these resources. Here is an example of the try-catch block with this improvement:

```java
try (MyResource mr = new MyResource()) {
System.out.println("MyResource created in try-with-resources");
} catch (Exception e) {
e.printStackTrace();
}
```

**A Custom Exception Class Example**

Java provides a lot of exception classes for us to use, but sometimes we may need to create our own custom exception classes. For example, to notify the caller about a specific type of exception with the appropriate message. We can have custom fields for tracking, such as error codes. For example, let’s say we write a method to process only text files, so we can provide the caller with the appropriate error code when some other type of file is sent as input.

First, create MyException:

MyException.java

```java
package com.journaldev.exceptions;
public class MyException extends Exception {
private static final long serialVersionUID = 4664456874499611218L;
private String errorCode = "Unknown_Exception";
public MyException(String message, String errorCode) {
super(message);
this.errorCode=errorCode;
}
public String getErrorCode() {
return this.errorCode;
}
}
Then, create a CustomExceptionExample:
CustomExceptionExample.java
package com.journaldev.exceptions;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
import java.io.IOException;
import java.io.InputStream;
public class CustomExceptionExample {
public static void main(String[] args) throws MyException {
try {
processFile("file.txt");
} catch (MyException e) {
processErrorCodes(e);
}
}
private static void processErrorCodes(MyException e) throws MyException {
switch (e.getErrorCode()) {
case "BAD_FILE_TYPE":
System.out.println("Bad File Type, notify user");
throw e;
case "FILE_NOT_FOUND_EXCEPTION":
System.out.println("File Not Found, notify user");
throw e;
case "FILE_CLOSE_EXCEPTION":
System.out.println("File Close failed, just log it.");
break;
default:
System.out.println("Unknown exception occured, lets log it for further debugging." + e.getMessage());
e.printStackTrace();
}
}
private static void processFile(String file) throws MyException {
InputStream fis = null;
try {
fis = new FileInputStream(file);
} catch (FileNotFoundException e) {
throw new MyException(e.getMessage(), "FILE_NOT_FOUND_EXCEPTION");
} finally {
try {
if (fis != null) fis.close();
} catch (IOException e) {
throw new MyException(e.getMessage(), "FILE_CLOSE_EXCEPTION");
}
}
}
}
```

We can have a separate method to process different types of error codes that we get from different methods. Some of them get consumed because we might not want to notify the user of that, or some of them we will throwback to notify the user of the problem.

Here I am extending Exception so that whenever this exception is being produced, it has to be handled in the method or returned to the caller program. If we extend RuntimeException, there is no need to specify it in the throws clause.

This was a design decision. Using Checked Exceptions has the advantage of assisting developers with understanding which exceptions you can expect and take appropriate action to handle them.

## Best Practices for Exception Handling in Java

-   **Use Specific Exceptions** – Base classes of Exception hierarchy don’t provide any useful information, that’s why Java has so many exception classes, such as IOException with further sub-classes as FileNotFoundException, EOFException, etc. We should always throw and catch specific exception classes so that caller will know the root cause of the exception easily and process them. This makes debugging easier and helps client applications handle exceptions appropriately.
-   **Throw Early or Fail-Fast** – We should try to throw exceptions as early as possible. Consider the above processFile() method, if we pass the null argument to this method, we will get the following exception:

**Output**

```
Exception in thread "main" java.lang.NullPointerException
at java.io.FileInputStream.<init>(FileInputStream.java:134)
at java.io.FileInputStream.<init>(FileInputStream.java:97)
at com.journaldev.exceptions.CustomExceptionExample.processFile(CustomExceptionExample.java:42)
at com.journaldev.exceptions.CustomExceptionExample.main(CustomExceptionExample.java:12)
```

While debugging we will have to look out at the stack trace carefully to identify the actual location of exception. If we change our implementation logic to check for these exceptions early as below:

```java
private static void processFile(String file) throws MyException {
if (file == null) throw new MyException("File name can't be null", "NULL_FILE_NAME");
// ... further processing
}
```

Then the exception stack trace will be indicate where the exception has occurred with clear message:

Output

```
com.journaldev.exceptions.MyException: File name can't be null
at com.journaldev.exceptions.CustomExceptionExample.processFile(CustomExceptionExample.java:37)
at com.journaldev.exceptions.CustomExceptionExample.main(CustomExceptionExample.java:12)
```

-   **Catch Late** – Since Java enforces to either handle the checked exception or to declare it in the method signature, sometimes developers tend to catch the exception and log the error. But this practice is harmful because the caller program doesn’t get any notification for the exception. We should catch exceptions only when we can handle them appropriately. For example, in the above method, I am throwing exceptions back to the caller method to handle it. The same method could be used by other applications that might want to process the exception in a different manner. While implementing any feature, we should always throw exceptions back to the caller and let them decide how to handle it.
-   **Closing Resources** – Since exceptions halt the processing of the program, we should close all the resources in finally block or use Java 7 try-with-resources enhancement to let java runtime close it for you.
-   **Logging Exceptions** – We should always log exception messages and while throwing exceptions provide a clear message so that caller will know easily why the exception occurred. We should always avoid an empty catch block that just consumes the exception and doesn’t provide any meaningful details of the exception for debugging.
-   **Single catch block for multiple exceptions** – Most of the time we log exception details and provide a message to the user, in this case, we should use Java 7 feature for handling multiple exceptions in a single catch block. This approach will reduce our code size, and it will look cleaner too.
-   **Using Custom Exceptions** – It’s always better to define an exception handling strategy at the design time and rather than throwing and catching multiple exceptions, we can create a custom exception with an error code, and the caller program can handle these error codes. It’s also a good idea to create a utility method to process different error codes and use them.
-   **Naming Conventions and Packaging** – When you create your custom exception, make sure it ends with Exception so that it will be clear from the name itself that it’s an exception class. Also, make sure to package them like it’s done in the Java Development Kit (JDK). For example, IOException is the base exception for all IO operations.
-   **Use Exceptions Judiciously** – Exceptions are costly, and sometimes it’s not required to throw exceptions at all, and we can return a boolean variable to the caller program to indicate whether an operation was successful or not. This is helpful where the operation is optional, and you don’t want your program to get stuck because it fails. For example, while updating the stock quotes in the database from a third-party web service, we may want to avoid throwing exceptions if the connection fails.
-   **Document the Exceptions Thrown** – Use Javadoc @throws to clearly specify the exceptions thrown by the method. It’s very helpful when you are providing an interface for other applications to use.

## References

1.  https://www.digitalocean.com/community/tutorials/exception-handling-in-java
