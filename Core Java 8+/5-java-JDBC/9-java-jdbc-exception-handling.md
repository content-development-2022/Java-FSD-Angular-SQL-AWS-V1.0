# JDBC Exceptions Handling

**Content**

[1. JDBC Exceptions Handling](#1-jdbc-exceptions-handling)

[2. SQLException Methods](#2-sqlexception-methods)

[3. References](#3-references)

# 1. JDBC Exceptions Handling

-   Exception handling allows you to handle exceptional conditions such as program-defined errors in a controlled fashion.
-   When an exception condition occurs, an exception is thrown.
-   The term thrown means that current program execution stops, and the control is redirected to the nearest applicable catch clause.
-   If no applicable catch clause exists, then the program's execution ends.
-   JDBC Exception handling is very similar to the Java Exception handling but for JDBC, the most common exception you'll deal with is **java.sql.SQLException.**

# 2. SQLException Methods

-   An SQLException can occur both in the driver and the database.
-   When such an exception occurs, an object of type SQLException will be passed to the catch clause.
-   The passed SQLException object has the following methods available for retrieving additional information about the exception:

| **Method**                     | **Description**                                                                                                                                                                                                 |
|--------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| getErrorCode( )                | Gets the error number associated with the exception.                                                                                                                                                            |
| getMessage( )                  | Gets the JDBC driver's error message for an error, handled by the driver or gets the Oracle error number and message for a database error.                                                                      |
| getSQLState( )                 | Gets the XOPEN SQLstate string. For a JDBC driver error, no useful information is returned from this method. For a database error, the five-digit XOPEN SQLstate code is returned. This method can return null. |
| getNextException( )            | Gets the next Exception object in the exception chain.                                                                                                                                                          |
| printStackTrace( )             | Prints the current exception, or throwable, and it's backtrace to a standard error stream.                                                                                                                      |
| printStackTrace(PrintStream s) | Prints this throwable and its backtrace to the print stream you specify.                                                                                                                                        |
| printStackTrace(PrintWriter w) | Prints this throwable and it's backtrace to the print writer you specify.                                                                                                                                       |

-   By utilizing the information available from the Exception object, you can catch an exception and continue your program appropriately.
-   Here is the general form of a try block:

```java
try {
    // Your risky code goes between these curly braces!!!
}
catch(Exception ex) {
    // Your exception handling code goes between these
    // curly braces, similar to the exception clause
    // in a PL/SQL block.
}
finally {
    // Your must-always-be-executed code goes between these
    // curly braces. Like closing database connection.
}
```

**Example**

-   Study the following example code to understand the usage of **try....catch...finally** blocks.

```java
import java.sql.CallableStatement;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
public class JDBCExample {
    static final String DB_URL = "jdbc:mysql://localhost/TUTORIALSPOINT";
    static final String USER = "guest";
    static final String PASS = "guest123";
    static final String QUERY = "{call getEmpName (?, ?)}";
    public static void main(String[] args) {
        // Open a connection
        try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
        CallableStatement stmt = conn.prepareCall(QUERY);
        ) {
            // Bind values into the parameters.
            stmt.setInt(1, 1); // This would set ID
            // Because second parameter is OUT so register it
            stmt.registerOutParameter(2, java.sql.Types.VARCHAR);
            //Use execute method to run stored procedure.
            System.out.println("Executing stored procedure..." );
            stmt.execute();
            //Retrieve employee name with getXXX method
            String empName = stmt.getString(2);
            System.out.println("Emp Name with ID: 1 is " + empName);
          } catch (SQLException e) {
                e.printStackTrace();
        }
    }
}
```

-   Now, let us compile the above example as follows −

```
C:\>javac JDBCExample.java
C:\>
```

-   When you run **JDBCExample**, it produces the following result if there is no problem, otherwise the corresponding error would be caught and error message would be displayed:

```
C:\>java JDBCExample
Executing stored procedure...
Emp Name with ID: 1 is Zara
C:\>
```

-   Try the above example by passing wrong database name or wrong username or password and check the result.

# 3. References

1.  https://www.tutorialspoint.com/jdbc/jdbc-exceptions.htm
