# Custom Exceptions

**Content**

[1. Custom Exceptions](#1-custom-exceptions)

[2. Best Practices for Exception Handling in Java](#2-best-practices-for-exception-handling-in-java)

[3. References](#3-references)

# 1. Custom Exceptions

-   Java provides a lot of exception classes for us to use, but sometimes we may need to create our own custom exception classes.
-   For example, to notify the caller about a specific type of exception with the appropriate message.
-   We can have custom fields for tracking, such as error codes.
-   For example, let’s say we write a method to process only text files, so we can provide the caller with the appropriate error code when some other type of file is sent as input.
**Step 1:** First, create Exception

**Example:**

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
 ```
 
 **Step 2:** Then, create a CustomException

**Example:**
 
```java
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

-   We can have a separate method to process different types of error codes that we get from different methods.
-   Some of them get consumed because we might not want to notify the user of that, or some of them we will throwback to notify the user of the problem.
-   Here I am extending Exception so that whenever this exception is being produced, it has to be handled in the method or returned to the caller program.
-   If we extend RuntimeException, there is no need to specify it in the throws clause.
-   This was a design decision.
-   Using Checked Exceptions has the advantage of assisting developers with understanding which exceptions you can expect and take appropriate action to handle them.

## 2. Best Practices for Exception Handling in Java

**1) Use Specific Exceptions**

-   Base classes of Exception hierarchy don’t provide any useful information, that’s why Java has so many exception classes, such as IOException with further sub-classes as FileNotFoundException, EOFException, etc.
-   We should always throw and catch specific exception classes so that caller will know the root cause of the exception easily and process them.
-   This makes debugging easier and helps client applications handle exceptions appropriately.

**2) Throw Early or Fail-Fast**

-   We should try to throw exceptions as early as possible.
-   Consider the above processFile() method, if we pass the null argument to this method, we will get the following exception:

**Output**

```
Exception in thread "main" java.lang.NullPointerException
at java.io.FileInputStream.<init>(FileInputStream.java:134)
at java.io.FileInputStream.<init>(FileInputStream.java:97)
at com.journaldev.exceptions.CustomExceptionExample.processFile(CustomExceptionExample.java:42)
at com.journaldev.exceptions.CustomExceptionExample.main(CustomExceptionExample.java:12)
```

-   While debugging we will have to look out at the stack trace carefully to identify the actual location of exception.
-   If we change our implementation logic to check for these exceptions early as below:

```java
private static void processFile(String file) throws MyException {
if (file == null) throw new MyException("File name can't be null", "NULL_FILE_NAME");
// ... further processing
}
```

-   Then the exception stack trace will be indicate where the exception has occurred with clear message:

**Output**

```
com.journaldev.exceptions.MyException: File name can't be null
at com.journaldev.exceptions.CustomExceptionExample.processFile(CustomExceptionExample.java:37)
at com.journaldev.exceptions.CustomExceptionExample.main(CustomExceptionExample.java:12)
```

**3) Catch Late**

-   Since Java enforces to either handle the checked exception or to declare it in the method signature, sometimes developers tend to catch the exception and log the error.
-   But this practice is harmful because the caller program doesn’t get any notification for the exception.
-   We should catch exceptions only when we can handle them appropriately.
-   For example, in the above method, I am throwing exceptions back to the caller method to handle it.
-   The same method could be used by other applications that might want to process the exception in a different manner.
-   While implementing any feature, we should always throw exceptions back to the caller and let them decide how to handle it.

**4) Closing Resources**

-   Since exceptions halt the processing of the program, we should close all the resources in finally block or use Java 7 try-with-resources enhancement to let java runtime close it for you.

**5) Logging Exceptions**

-   We should always log exception messages and while throwing exceptions provide a clear message so that caller will know easily why the exception occurred.
-   We should always avoid an empty catch block that just consumes the exception and doesn’t provide any meaningful details of the exception for debugging.

**6) Single catch block for multiple exceptions**:

-   Most of the time we log exception details and provide a message to the user, in this case, we should use Java 7 feature for handling multiple exceptions in a single catch block.
-   This approach will reduce our code size, and it will look cleaner too.

**7) Using Custom Exceptions**:

-   It’s always better to define an exception handling strategy at the design time and rather than throwing and catching multiple exceptions, we can create a custom exception with an error code, and the caller program can handle these error codes.
-   It’s also a good idea to create a utility method to process different error codes and use them.

**8) Naming Conventions and Packaging**:

-   When you create your custom exception, make sure it ends with Exception so that it will be clear from the name itself that it’s an exception class.
-   Also, make sure to package them like it’s done in the Java Development Kit (JDK).
-   For example, IOException is the base exception for all IO operations.

**9) Use Exceptions Judiciously**:

-   Exceptions are costly, and sometimes it’s not required to throw exceptions at all, and we can return a boolean variable to the caller program to indicate whether an operation was successful or not.
-   This is helpful where the operation is optional, and you don’t want your program to get stuck because it fails.
-   For example, while updating the stock quotes in the database from a third-party web service, we may want to avoid throwing exceptions if the connection fails.

**10) Document the Exceptions Thrown**

-   Use Javadoc @throws to clearly specify the exceptions thrown by the method.
-   It’s very helpful when you are providing an interface for other applications to use.

## 3. References

1.  https://www.digitalocean.com/community/tutorials/exception-handling-in-java
