# JDBC Stored Procedure

**Content**

[1. JDBC Stored Procedure](#1-jdbc-stored-procedure)

[2. JDBC SQL Escape Syntax](#2-jdbc-sql-escape-syntax)

[3. References](#3-references)

# 1. JDBC Stored Procedure

-   We have learnt how to use **Stored Procedures** in JDBC while discussing the JDBC statements.
-   This topic is similar to that section, but it would gives you additional information about JDBC SQL escape syntax.

# 2. JDBC SQL Escape Syntax

-   The escape syntax gives you the flexibility to use database specific features unavailable to you by using standard JDBC methods and properties.
-   The general SQL escape syntax format is as follows:

```java
{keyword 'parameters'}
```

-   Here are the following escape sequences, which you would find very useful while performing the JDBC programming:

## 2.1 d, t, ts Keywords

-   They help identify date, time, and timestamp literals.
-   As you know, no two DBMSs represent time and date the same way.
-   This escape syntax tells the driver to render the date or time in the target database's format.

**Example:**

```sql
{d 'yyyy-mm-dd'}
```

-   Where yyyy = year, mm = month; dd = date.
-   Using this syntax {d '2009-09-03'} is March 9, 2009.
-   Here is a simple example showing how to INSERT date in a table:

```sql
//Create a Statement object
stmt = conn.createStatement();
//Insert data ==> ID, First Name, Last Name, DOB
String sql="INSERT INTO STUDENTS VALUES" +"(100,'Zara','Ali', {d '2001-12-16'})";
stmt.executeUpdate(sql);
```

-   Similarly, you can use one of the following two syntaxes, either **t** or **ts**:

```sql
{t 'hh:mm:ss'}
```

-   Where hh = hour; mm = minute; ss = second.
-   Using this syntax {t '13:30:29'} is 1:30:29 PM.

```sql
{ts 'yyyy-mm-dd hh:mm:ss'}
```

-   This is combined syntax of the above two syntax for 'd' and 't' to represent timestamp.

## 2.2 escape Keyword

-   This keyword identifies the escape character used in LIKE clauses.
-   Useful when using the SQL wildcard %, which matches zero or more characters.

**Example:**

```sql
String sql = "SELECT symbol FROM MathSymbols
WHERE symbol LIKE '\%' {escape '\'}";
stmt.execute(sql);
```

-   If you use the backslash character (\\) as the escape character, you also have to use two backslash characters in your Java String literal, because the backslash is also a Java escape character.

## 2.3 fn Keyword

-   This keyword represents scalar functions used in a DBMS.
-   For example, you can use SQL function *length* to get the length of a string:

```sql
{fn length('Hello World')}
```

-   This returns 11, the length of the character string 'Hello World'.

## 2.4 call Keyword

-   This keyword is used to call the stored procedures.
-   For example, for a stored procedure requiring an IN parameter, use the following syntax:

```sql
{call my_procedure(?)};
```

-   For a stored procedure requiring an IN parameter and returning an OUT parameter, use the following syntax:

```sql
{? = call my_procedure(?)};
```

## 2.5 oj Keyword

-   This keyword is used to signify outer joins.
-   The syntax is as follows:

```sql
{oj outer-join}
```

-   Where outer-join = table {LEFT\|RIGHT\|FULL} OUTERJOIN {table \| outer-join} on search-condition.

**Example:**

```sql
String sql = "SELECT Employees
FROM {oj ThisTable RIGHT
OUTER JOIN ThatTable on id = '100'}";
stmt.execute(sql);
```

# 3. References

1.  https://www.tutorialspoint.com/jdbc/jdbc-stored-procedure.htm
