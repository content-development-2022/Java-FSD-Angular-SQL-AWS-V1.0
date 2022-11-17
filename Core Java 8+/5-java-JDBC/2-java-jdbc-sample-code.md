# JDBC – Sample Code

[1. Creating JDBC Application](#1-creating-jdbc-application)

[2. Sample Code](#2-sample-code)

[3. References](#3-references)

# 1. Creating JDBC Application

There are following six steps involved in building a JDBC application:

-   **Import the packages** − Requires that you include the packages containing the JDBC classes needed for database programming. Most often, using *import java.sql.\** will suffice.
-   **Open a connection** − Requires using the *DriverManager.getConnection()* method to create a Connection object, which represents a physical connection with the database.
-   **Execute a query** − Requires using an object of type Statement for building and submitting an SQL statement to the database.
-   **Extract data from result set** − Requires that you use the appropriate *ResultSet.getXXX()* method to retrieve the data from the result set.
-   **Clean up the environment** − Requires explicitly closing all database resources versus relying on the JVM's garbage collection.

# 2. Sample Code

-   This sample example can serve as a **template** when you need to create your own JDBC application in the future.
-   This sample code has been written based on the environment and database setup done in the previous chapter.
-   Copy and paste the following example in FirstExample.java, compile and run as follows:

```java
import java.sql.*;
public class FirstExample {
static final String DB_URL = "jdbc:mysql://localhost/TUTORIALSPOINT";
static final String USER = "guest";
static final String PASS = "guest123";
static final String QUERY = "SELECT id, first, last, age FROM Employees";
public static void main(String[] args) {
// Open a connection
try(Connection conn = DriverManager.getConnection(DB_URL, USER, PASS);
Statement stmt = conn.createStatement();
ResultSet rs = stmt.executeQuery(QUERY);) {
// Extract data from result set
while (rs.next()) {
// Retrieve by column name
System.out.print("ID: " + rs.getInt("id"));
System.out.print(", Age: " + rs.getInt("age"));
System.out.print(", First: " + rs.getString("first"));
System.out.println(", Last: " + rs.getString("last"));
}
} catch (SQLException e) {
e.printStackTrace();
}
}
}
```

-   Now let us compile the above example as follows −

```
C:\>javac FirstExample.java
C:\>
```

-   When you run **FirstExample**, it produces the following result −

```
C:\>java FirstExample
Connecting to database...
Creating statement...
ID: 100, Age: 18, First: Zara, Last: Ali
ID: 101, Age: 25, First: Mahnaz, Last: Fatma
ID: 102, Age: 30, First: Zaid, Last: Khan
ID: 103, Age: 28, First: Sumit, Last: Mittal
C:\>
```

# 3. References

1.  https://www.tutorialspoint.com/jdbc/jdbc-sample-code.htm
