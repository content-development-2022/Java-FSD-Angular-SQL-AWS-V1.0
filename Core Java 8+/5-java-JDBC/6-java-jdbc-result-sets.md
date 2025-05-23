# JDBC - Result Sets

**Content**

[1. JDBC Result Sets](#1-jdbc-result-sets)

[2. Type of ResultSet](#2-type-of-resultset)

[2.1 Concurrency of ResultSet](#21-concurrency-of-resultset)

[2.2 Navigating a Result Set](#22-navigating-a-result-set)

[2.3 Viewing a Result Set](#23-viewing-a-result-set)

[2.4 Updating a Result Set](#24-updating-a-result-set)

[3. References](#3-references)

# 1. JDBC Result Sets

-   The SQL statements that read data from a database query, return the data in a result set.
-   The SELECT statement is the standard way to select rows from a database and view them in a result set.
-   The *java.sql.ResultSet* interface represents the result set of a database query.
-   A ResultSet object maintains a cursor that points to the current row in the result set.
-   The term "result set" refers to the row and column data contained in a ResultSet object.
-   The methods of the ResultSet interface can be broken down into three categories:
1.  **Navigational methods** − Used to move the cursor around.
2.  **Get methods** − Used to view the data in the columns of the current row being pointed by the cursor.
3.  **Update methods** − Used to update the data in the columns of the current row. The updates can then be updated in the underlying database as well.
-   The cursor is movable based on the properties of the ResultSet.
-   These properties are designated when the corresponding Statement that generates the ResultSet is created.
-   JDBC provides the following connection methods to create statements with desired ResultSet
1.  **createStatement(int RSType, int RSConcurrency);**
2.  **prepareStatement(String SQL, int RSType, int RSConcurrency);**
3.  **prepareCall(String sql, int RSType, int RSConcurrency);**
-   The first argument indicates the type of a ResultSet object and the second argument is one of two ResultSet constants for specifying whether a result set is read-only or updatable.

# 2. Type of ResultSet

-   The possible RSType are given below.
-   If you do not specify any ResultSet type, you will automatically get one that is TYPE_FORWARD_ONLY.

| **Type**                          | **Description**                                                                                                                                                        |
|-----------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ResultSet.TYPE_FORWARD_ONLY       | The cursor can only move forward in the result set.                                                                                                                    |
| ResultSet.TYPE_SCROLL_INSENSITIVE | The cursor can scroll forward and backward, and the result set is not sensitive to changes made by others to the database that occur after the result set was created. |
| ResultSet.TYPE_SCROLL_SENSITIVE.  | The cursor can scroll forward and backward, and the result set is sensitive to changes made by others to the database that occur after the result set was created.     |

## 2.1 Concurrency of ResultSet

-   The possible RSConcurrency are given below.
-   If you do not specify any Concurrency type, you will automatically get one that is CONCUR_READ_ONLY.

| **Concurrency**            | **Description**                                     |
|----------------------------|-----------------------------------------------------|
| ResultSet.CONCUR_READ_ONLY | Creates a read-only result set. This is the default |
| ResultSet.CONCUR_UPDATABLE | Creates an updateable result set.                   |

-   All our examples written so far can be written as follows, which initializes a Statement object to create a forward-only, read only ResultSet object

```java
try {
    Statement stmt = conn.createStatement(ResultSet.TYPE_FORWARD_ONLY, ResultSet.CONCUR_READ_ONLY);
}
catch(Exception ex) {
    ....
}
finally {
    ....
}
```

## 2.2 Navigating a Result Set

-   There are several methods in the ResultSet interface that involve moving the cursor, including

| **S.N.** | **Methods & Description**                                                                                                                                                                                    |
|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1        | **public void beforeFirst() throws SQLException** Moves the cursor just before the first row.                                                                                                                |
| 2        | **public void afterLast() throws SQLException** Moves the cursor just after the last row.                                                                                                                    |
| 3        | **public boolean first() throws SQLException** Moves the cursor to the first row.                                                                                                                            |
| 4        | **public void last() throws SQLException** Moves the cursor to the last row.                                                                                                                                 |
| 5        | **public boolean absolute(int row) throws SQLException** Moves the cursor to the specified row.                                                                                                              |
| 6        | **public boolean relative(int row) throws SQLException** Moves the cursor the given number of rows forward or backward, from where it is currently pointing.                                                 |
| 7        | **public boolean previous() throws SQLException** Moves the cursor to the previous row. This method returns false if the previous row is off the result set.                                                 |
| 8        | **public boolean next() throws SQLException** Moves the cursor to the next row. This method returns false if there are no more rows in the result set.                                                       |
| 9        | **public int getRow() throws SQLException** Returns the row number that the cursor is pointing to.                                                                                                           |
| 10       | **public void moveToInsertRow() throws SQLException** Moves the cursor to a special row in the result set that can be used to insert a new row into the database. The current cursor location is remembered. |
| 11       | **public void moveToCurrentRow() throws SQLException** Moves the cursor back to the current row if the cursor is currently at the insert row; otherwise, this method does nothing                            |

## 2.3 Viewing a Result Set

-   The ResultSet interface contains dozens of methods for getting the data of the current row.
-   There is a get method for each of the possible data types, and each get method has two versions
1.  One that takes in a column name.
2.  One that takes in a column index.
-   For example, if the column you are interested in viewing contains an int, you need to use one of the getInt() methods of ResultSet

| **S.N.** | **Methods & Description**                                                                                                                                                                                                                      |
|----------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1        | **public int getInt(String columnName) throws SQLException** Returns the int in the current row in the column named columnName.                                                                                                                |
| 2        | **public int getInt(int columnIndex) throws SQLException** Returns the int in the current row in the specified column index. The column index starts at 1, meaning the first column of a row is 1, the second column of a row is 2, and so on. |

-   Similarly, there are get methods in the ResultSet interface for each of the eight Java primitive types, as well as common types such as java.lang.String, java.lang.Object, and java.net.URL.
-   There are also methods for getting SQL data types java.sql.Date, java.sql.Time, java.sql.TimeStamp, java.sql.Clob, and java.sql.Blob.

## 2.4 Updating a Result Set

-   The ResultSet interface contains a collection of update methods for updating the data of a result set.
-   As with the get methods, there are two update methods for each data type
1.  One that takes in a column name.
2.  One that takes in a column index.
-   For example, to update a String column of the current row of a result set, you would use one of the following updateString() methods

| **S.N.** | **Methods & Description**                                                                                                                                                           |
|----------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1        | **public void updateString(int columnIndex, String s) throws SQLException** Changes the String in the specified column to the value of s.                                           |
| 2        | **public void updateString(String columnName, String s) throws SQLException** Similar to the previous method, except that the column is specified by its name instead of its index. |

-   There are update methods for the eight primitive data types, as well as String, Object, URL, and the SQL data types in the java.sql package.
-   Updating a row in the result set changes the columns of the current row in the ResultSet object, but not in the underlying database.
-   To update your changes to the row in the database, you need to invoke one of the following methods.

| **S.N.** | **Methods & Description**                                                                                                                   |
|----------|---------------------------------------------------------------------------------------------------------------------------------------------|
| 1        | **public void updateRow()** Updates the current row by updating the corresponding row in the database.                                      |
| 2        | **public void deleteRow()** Deletes the current row from the database                                                                       |
| 3        | **public void refreshRow()** Refreshes the data in the result set to reflect any recent changes in the database.                            |
| 4        | **public void cancelRowUpdates()** Cancels any updates made on the current row.                                                             |
| 5        | **public void insertRow()** Inserts a row into the database. This method can only be invoked when the cursor is pointing to the insert row. |

# 3. References

1.  https://www.tutorialspoint.com/jdbc/jdbc-result-sets.htm
