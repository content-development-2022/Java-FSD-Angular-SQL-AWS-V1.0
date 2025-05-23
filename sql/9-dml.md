## DML (Data Manipulation Language)

**Content**

**1. DML**

**2. DML Commands**

**2.1 PostgreSQL INSERT**

2.1.1 RETURNING Clause

2.1.2 PostgreSQL INSERT statement examples

2.1.3 PostgreSQL INSERT Multiple Rows

2.1.3.1 Inserting multiple rows example

**2.2 PostgreSQL UPDATE**

2.2.1 Returning updated rows

2.2.2 PostgreSQL UPDATE examples

**2.3 PostgreSQL DELETE**

2.3.1 PostgreSQL DELETE statement examples

2.3.2 Difference between Delete, Truncate and Drop Commands

3\. References

## 1. DML

-   A **data manipulation language** (**DML**) is a computer programming language used for adding (inserting), deleting, and modifying (updating) data in a database.

## 2. DML Commands

-   **INSERT** : It is used to insert data into a table.
-   **UPDATE:** It is used to update existing data within a table.
-   **DELETE** : It is used to delete records from a database table.

## 2.1 PostgreSQL INSERT

-   The PostgreSQL INSERT statement allows you to insert **a new row** into a table.
-   The following illustrates the most basic syntax of the INSERT statement:

![](media/e4f87d9180d811f0cab568d2520c47ac.png)

In this syntax:

-   **First,** specify the **name of the table** (table_name) that you want to insert data after the **INSERT INTO** keywords and a list of comma-separated columns (colum1, column2, ....).
-   **Second,** supply a list of comma-separated **values** in a parentheses (value1, value2, ...) after the **VALUES** keyword. The columns and values in the column and value lists must be in the same order.

**The INSERT statement returns a command tag with the following form:**

![](media/a64a31f762d9e590c4482811cd8e7ed4.png)

-   **OID** is an **object identifier**. PostgreSQL used the OID internally as a primary key for its system tables. Typically, the INSERT statement returns OID with value 0. The count is the number of rows that the INSERT statement inserted successfully.

## 2.1.1 RETURNING Clause

-   The INSERT statement also has an optional RETURNING clause that returns the **information of the inserted row**.
-   If you want to return the **entire inserted row**, you use an asterisk **(\*)** after the RETURNING keyword:

![](media/d5d29233624f0c04a4608189918a43cd.png)

-   If you want to return just **some information of the inserted row**, you can **specify one or more columns** after the RETURNING clause.

For example, the following statement returns the id of the inserted row:

![](media/aa2fbb0d73132c5ec7272ff33d0063e9.png)

-   To **rename the returned value**, you use the **AS** keyword followed by the name of the output.

For example:

![](media/fe117e64a9fdf899fceb2e44fca3c5e2.png)

## 2.1.2 PostgreSQL INSERT statement examples

-   The following statement **creates a new table** called **links** for the demonstration:

![](media/a96958695653f6aeec6398d16529643f.png)

## 1) PostgreSQL INSERT – Inserting a single row into a table

-   The following statement inserts a new row into the links table:

![](media/6e9dc88bf039a9d08fc2012c97ea6d3e.png)

-   The statement returns the following **output**:

![](media/a19fd4291c4a9087dc0ba75a66d477c1.png)

-   To insert **character data**, you enclose it in single quotes **(‘)** for example 'PostgreSQL Tutorial'.
-   If you **omit required columns** in the INSERT statement, PostgreSQL will **issue an error**. In case you **omit an optional column**, PostgreSQL will use the column **default value** for insert.
-   In the above example, the **description is an optional column** because it doesn’t have a NOT NULL constraint. Therefore, PostgreSQL uses **NULL** to insert into the description column.
-   PostgreSQL **automatically** generates a **sequential number** for the serial column so you do not have to supply a value for the serial column in the INSERT statement.

The following SELECT statement shows the contents of the links table:

![](media/17bb6659d42789c00ad2ad95d5a3742e.png)

**Output**

![](media/13473332878f076fc85d867cc573b364.png)

## 2) PostgreSQL INSERT – Inserting character string that contains a single quote

-   If you want to **insert a string** that **contains** a single quote **(')** such as **O'Reilly Media**, you have to use an additional single quote (') to escape it. For example:

![](media/2ac8da5cbd0389084541071abdc4900b.png)

**Output:**

![](media/560089f4d46730f5b4098835f1bfb1d4.png)

-   The following statement verifies the insert:

![](media/16717a9b3253fbe580237a063a1a2c9e.png)

## 3) PostgreSQL INSERT – Inserting a date value

-   To insert a **date** value into a column with the **DATE type**, you use the date in the format **'YYYY-MM-DD'**.
-   The following statement inserts a new row with a specified date into the links table:

![](media/19897d9e350966d64256da0fa6f3d0dc.png)

**Output:**

![](media/724bb4c1d3f1f23e0d04d6f3398e82a3.png)

## 4) PostgreSQL INSERT- Getting the last insert id

-   To get the **last insert id** from inserted row, you **use** the **RETURNING** clause of the INSERTstatement.
-   For example, the following statement inserts a new row into the links table and returns the last insert id:

![](media/e580b9a8748de7c083d39918480d4f82.png)

Output:

![](media/dbe81f68cf7e9a3e644366e391e24bc9.png)

## 2.1.3 PostgreSQL INSERT Multiple Rows

-   To insert multiple rows into a table using a single INSERT statement, you use the following syntax:

![](media/fba0e0e678d802de43747772046db215.png)

-   To **insert multiple rows** and **return the inserted rows**, you add the RETURNING clause as follows:

![](media/9182fc72c32eeb30d9f4b661fa46c803.png)

## 2.1.3.1 Inserting multiple rows example

-   The following statement uses the INSERT statement to **add three rows** to the links table:

![](media/56c55190de0b02089c7b3cf1826f5613.png)

-   PostgreSQL returns the following message:

![](media/42b90632dcb3a0a4713a694258e46607.png)

-   To verify the inserts, you use the following statement:

![](media/08c0309f73e9430cd16a516f14801441.png)

**Output:**

![](media/03d4ec47d779421f3ef77694ac420475.png)

## 1) Inserting multiple rows and returning inserted rows

-   The following statement uses the INSERT statement to **insert two rows** into the links table and **returns** the **inserted rows:**

![](media/bcad2651a35277c6069c2db0858aea47.png)

![](media/8d8c0a01569af4c277013c71773a75eb.png)

-   If you just want to **return the inserted id list**, you can specify the id column in the RETURNING clause like this:

![](media/f92cfb727b7df9f8f81d696528f90992.png)

![](media/4f4eba96aed17b66d1ed24356e117ce3.png)

## 2.2 PostgreSQL UPDATE

-   The PostgreSQL UPDATE statement allows you to **modify data** in a table.
-   The following illustrates the syntax of the UPDATE statement:

![](media/0b1279b6dca9d1fe56c94238e3b1dd9a.png)

In this syntax:

-   **First,** specify the **name of the table** that you want to update data after the UPDATE keyword.
-   **Second,** specify columns and their **new values** after **SET** keyword. The columns that do not appear in the SET clause retain their original values.
-   **Third,** determine which rows to update in the condition of the **WHERE** clause. The WHERE clause is optional. If you omit the WHERE clause, the UPDATE statement will update all rows in the table.

**When the UPDATE statement is executed successfully, it returns the following command tag:**

![](media/9a4137d180854cb64468bea5eae394f6.png)

-   The count is the number of rows updated including rows whose values did not change.

## 2.2.1 Returning updated rows

-   The UPDATE statement has an optional RETURNING clause that returns the updated rows:

![](media/c7159d47dba6be84d9d3b5056f0f2051.png)

## 2.2.2 PostgreSQL UPDATE examples

-   The following statements **create a table** called **courses** and **insert** some **data** into it:

![](media/6915f2a84eba2523d8d5e81d280a178a.png)

-   The following statement returns the data from the courses table:

![](media/d13fceec7464eae4d9f17e59a6595c91.png)

![](media/c57e4bc27a3c3cccd38abaed0fa702ec.png)

## 1) PostgreSQL UPDATE – updating one row

-   The following statement uses the UPDATE statement to update the course with id 3. It changes the published_date from NULL to '2020-08-01'.

![](media/8ffb7a037bec2b5317de53f0e6ca6bb2.png)

-   The statement returns the following message indicating that one row has been updated:

![](media/8c34eb68a841a75daab3cafe045da075.png)

-   The following statement selects the course with id 3 to verify the update:

![](media/8e22c42eda0cc5c3d51afc649318df0c.png)

![](media/71b34ddb8fbc3fe5161fa4fb6ea8e0ec.png)

## 2) PostgreSQL UPDATE – updating a row and returning the updated row

-   The following statement updates course id 2. It modifies published_date of the course to 2020-07-01 and returns the updated course.

![](media/7d6b07a4178184b9053ca23b4a920221.png)

![](media/420b166be4de431bd75e5d02e7f997e3.png)

## 2.3 PostgreSQL DELETE

-   The PostgreSQL DELETE statement allows you to **delete one or more rows** from a table.
-   The following shows basic syntax of the DELETE statement:

![](media/e73742cb81b5250c884c9c1bae806f57.png)

In this syntax:

1.  **First,** specify the **name of the table** from which you want to delete data after the DELETE FROM keywords.
2.  **Second,** use a **condition** in the WHERE clause to specify which rows from the table to delete.
-   The **WHERE** clause is optional. If you **omit** the WHERE clause, the DELETE statement will **delete all rows** in the table.
-   The DELETE statement returns the number of rows deleted. It returns **zero** if the DELETE statement **did not delete any row**.
-   To return the deleted row(s) to the client, you use the RETURNING clause as follows:

![](media/2b0d366974a5063aecc89fe40cb6170d.png)

-   The asterisk (**\***) allows you to **return all columns** of the deleted row from the table_name.
-   To return specific columns, you specify them after the RETURNING keyword.

![](media/11cbe093796299ded0198a65ab5960f4.png)

## 2.3.1 PostgreSQL DELETE statement examples

-   The following statements **create a new table** called **links** and **insert some** sample **data**:

![](media/1dfdfee73979802299720e1b5c87602d.png)

-   Here are the contents of the links table:

![](media/f1ad342306ebc31e0ef538d05ef610f0.png)

## 1) Using PostgreSQL DELETE to delete one row from the table

-   The following statement uses the DELETE statement to **delete one row** with the id 8 from the links table:

![](media/68f3667d3c58a742916447479744af4e.png)

-   The statement **returns 1** indicated that **one row** has been **deleted**:

![](media/2bbc2356aec8d1344e784e853e448104.png)

-   The following statement uses the DELETE statement to delete the row with id 10:

![](media/17e7dc1be3895f05e81c2ce305dcb3c6.png)

-   Since the row with **id 10 does not exist**, the statement **returns 0**:

![](media/f9d96e4bbba94b50136e9e751953ee13.png)

## 2) Using PostgreSQL DELETE to delete a row and return the deleted row

-   The following statement **deletes the row** with id 7 and returns the deleted row to the client:

![](media/4f4db55cb6eca7a06c1dc84e218d04e5.png)

-   PostgreSQL returns the following deleted row:

![](media/7939f0a341375528c95d3507806f514f.png)

## 3) Using PostgreSQL DELETE to delete multiple rows from the table

-   The following statement **deletes two rows** from the links table and return the values of deleted rows:

![](media/0f68e04ed1fb134def7ea90b3387498c.png)

## 4) Using PostgreSQL DELETE to delete all rows from the table

-   The following statement uses the DELETE statement without a WHERE clause to **delete all rows** from the links table:

![](media/b4d9e28a5e7837452ed4aadc0058c974.png)

-   The links table now is empty.

## 2.3.2 Difference between Delete, Truncate and Drop Commands

![](media/99c52f6d1f015339041afd4518dc4f70.png)

## 3. References

1.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-insert/
2.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-insert-multiple-rows/
3.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-update/
4.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-delete/
