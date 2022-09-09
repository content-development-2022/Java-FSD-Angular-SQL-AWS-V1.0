# DQL-Data Query Language

**Content**

**1. DQL (Data Query Language)**

**2. List of DQL Command**

**3. PostgreSQL SELECT and FROM Clause**

3.1 PostgreSQL SELECT and FROM Statement Syntax

3.2 PostgreSQL SELECT and FROM Examples

**4. PostgreSQL ORDER BY Clause**

4.1 PostgreSQL ORDER BY Examples

4.2 PostgreSQL ORDER BY Clause and NULL

**5. PostgreSQL WHERE Clause**

5.1 PostgreSQL WHERE Clause Examples

**6. PostgreSQL GROUP BY Clause**

6.1 PostgreSQL GROUP BY Clause Examples

**7. PostgreSQL HAVING Clause**

7.1 HAVING vs. WHERE

7.2 PostgreSQL HAVING Clause Examples

**8. References**

## 1. DQL (Data Query Language)

-   DQL or data query language is to perform the query on the data inside the schema or object (i.e table, index, view, function, etc).
-   With the help of DQL query we can get the data from the database to perform actions or operations like analysing the data.

## 2. List of DQL Command

-   **SELECT:** It is used to retrieve data from the database.

## 3. PostgreSQL SELECT and FROM Clause

-   One of the most common tasks, when you work with the database, is to query data from tables by using the SELECT statement.
-   The SELECT statement is one of the most complex statements in PostgreSQL. It has many clauses that you can use to form a flexible query.

The SELECT statement has the following clauses:

-   Sort rows using ORDER BY clause.
-   Filter rows using WHERE clause.
-   Group rows into groups using GROUP BY clause.
-   Filter groups using HAVING clause.

## 3.1 PostgreSQL SELECT and FROM Statement Syntax

-   Let’s start with the basic form of the SELECT statement that retrieves data from a single table.
-   The following illustrates the syntax of the SELECT statement:

![](media/83c59e80a3db86fdcbeb57d3968b38dc.png)

-   **First,** specify a select list that can be a column or a list of columns in a table from which you want to retrieve data. If you specify a list of columns, you need to place a comma (,) between two columns to separate them. If you want to select **data from all the columns** of the table, you can use an asterisk (**\***) shorthand instead of specifying all the column names. The select list may also contain expressions or literal values.
-   **Second,** specify the **name of the table** from which you want to query data after the **FROM** keyword.

The FROM clause is optional. If you do not query data from any table, you can omit the FROM clause in the SELECT statement.

-   PostgreSQL evaluates the FROM clause before the SELECT clause in the SELECT statement:

![](media/ecf0a60898d2d7597132690db2073b61.png)

## 3.2 PostgreSQL SELECT and FROM Examples

-   We will use the following **customer table** in the sample database for the demonstration.

![](media/8f9ac3167d4b3fb63f981a7368225916.png)

## 1) Using PostgreSQL SELECT statement to query data from one column

-   This example uses the SELECT statement to find the first names of all customers from the customer table:

![](media/ad5e925b774f2e3058f499cf2a199129.png)

**Output**

![](media/6ca8a0748fe19d1e4c1e1f31cc7b8579.png)

-   **Notice** that we added a semicolon (**;**) at the **end** of the **SELECT statement**. The semicolon is not a part of the SQL statement. It is used to **signal** PostgreSQL the end of an SQL statement. The semicolon is also used to **separate two SQL statements**.

## 2) Using PostgreSQL SELECT statement to query data from multiple columns

-   Suppose you just want to know the first name, last name and email of customers, you can specify these column names in the SELECT clause as shown in the following query:

![](media/181cc7ddead63290f3dea8f184aea03a.png)

**Output**

![](media/27260207d28e71e539b86a5d74db884c.png)

## 3) Using PostgreSQL SELECT statement to query data from all columns of a table

-   The following query uses the SELECT statement to select data from all columns of the customer table:

![](media/6d4259b2f8c9a8be3fe9fe43920d79b3.png)

**Output**

![](media/3981d649d042df18446925abf681655d.png)

-   In this example, we used an asterisk (\*) in the SELECT clause, which is a shorthand for all columns. Instead of listing all columns in the SELECT clause, we just used the asterisk (\*) to save some typing.

However, **it is not a good practice** to use the asterisk (**\***) in the SELECT statement when you embed SQL statements in the application code like Python, Java, Node.js, or PHP due to the following reasons:

1.  **Database performance.** Suppose you have a table with many columns and a lot of data, the SELECT statement with the asterisk (\*) shorthand will select data from all the columns of the table, which may not be necessary to the application.
2.  **Application performance.** Retrieving unnecessary data from the database increases the traffic between the database server and application server. In consequence, your applications may be slower to respond and less scalable.

Because of these reasons, it is a good practice to explicitly specify the column names in the SELECT clause whenever possible to get only necessary data from the database.

-   And you should only use the asterisk (\*) shorthand for the ad-hoc queries that examine data from the database.

## 4) Using PostgreSQL SELECT statement with expressions

-   The following example uses the SELECT statement to return full names and emails of all customers:

![](media/ea2766283931889e1530091f11d6f9ff.png)

**Output:**

![](media/4a3911db0f018152d6f6d438e7dcebd1.png)

-   In this example, we used the **concatenation operator** \|\| to concatenate the first name, space, and last name of every customer.

## 5) Using PostgreSQL SELECT statement with expressions and omits FROM clause

-   The following example uses the SELECT statement with an expression. It omits the FROM clause:

![](media/63e2c579f3956b59aad5835fc23318b5.png)

**Output**

![](media/6aae91215e8435b14237ab29feb89124.png)

## 4. PostgreSQL ORDER BY Clause

-   When you query data from a table, the SELECT statement returns rows in an unspecified order. To sort the rows of the result set, you use the ORDER BY clause in the SELECT statement.
-   The **ORDER BY** clause **allows** you to **sort rows** returned by a SELECT clause in **ascending or descending** order based on a sort expression.
-   The following illustrates the syntax of the ORDER BY clause:

![](media/e7444395ae99f06f818a766f09098092.png)

In this syntax:

-   **First,** specify a **sort expression**, which can be a column or an expression, that you want to sort after the ORDER BY keywords. If you want to sort the result set based on multiple columns or expressions, you need to place a comma (,) between two columns or expressions to separate them.
-   **Second,** you use the **ASC** option to **sort rows in ascending order** and the **DESC** option to **sort rows in descending order**. If you omit the ASC or DESC option, the ORDER BY uses **ASC by default**.

PostgreSQL evaluates the clauses in the SELECT statement in the following order: FROM, SELECT, and ORDER BY:

![](media/172fbb79a8262463faf70cda41ed9844.png)

-   Due to the order of evaluation, if you have a column alias in the SELECT clause, you can use it in the ORDER BY clause.

## 4.1 PostgreSQL ORDER BY Examples

-   We will use the customer table in the sample database for the demonstration.

### ![](media/212ca377510477ec951d557e5575b4d0.png)

## 1) Using PostgreSQL ORDER BY clause to sort rows by one column

-   The following query uses the ORDER BY clause to sort customers by their first names in ascending order:

![](media/44f2e733c49a42f7b4dd1ee23dd4e6cf.png)

**Output**

![](media/d013b868ac1dbad89bbfd0d80fc83895.png)

-   Since the ASC option is the default, you can omit it in the ORDER BY clause like this:

![](media/d896d451f8e50df84713342a84099a20.png)

## 2) Using PostgreSQL ORDER BY clause to sort rows by one column in descending order

-   The following statement selects the first name and last name from the customer table and sorts the rows by values in the last name column in descending order:

![](media/6c6df47971e24219080d0757ba62a23a.png)

**Output**

![](media/851ce18f8a489e3c10dd376813e2c480.png)

## 3) Using PostgreSQL ORDER BY clause to sort rows by multiple columns

-   The following statement selects the first name and last name from the customer table and sorts the rows by the first name in ascending order and last name in descending order:

![](media/94091828159547abd42f648d5448cc3b.png)

**Output**

![](media/325434a75bac543a64c4a873bc805c4c.png)

-   In this example, the ORDER BY clause sorts rows by values in the first name column first. And then it sorts the sorted rows by values in the last name column.
-   As you can see clearly from the output, two customers with the same first name Kelly have the last name sorted in descending order.

## 4) Using PostgreSQL ORDER BY clause to sort rows by expressions

-   The **LENGTH()** function accepts a string and returns the length of that string.
-   The following statement selects the first names and their lengths. It sorts the rows by the lengths of the first names:

![](media/e54513267e3a5969daff081eeca8c47c.png)

**Output**

![](media/f26116fca32bf9800bdb36041dc11c35.png)

-   Because the ORDER BY clause is evaluated after the SELECT clause, the column alias len is available and can be used in the ORDER BY clause.

## 4.2 PostgreSQL ORDER BY Clause and NULL

-   In the database world, NULL is a marker that indicates the missing data or the data is unknown at the time of recording.
-   When you sort rows that contains NULL, you can specify the order of NULL with other non-null values by using the NULLS FIRST or NULLS LAST option of the ORDER BY clause:

![](media/daf51f6884258f27e2cc44f2fb5117c9.png)

-   The NULLS FIRST option places NULL before other non-null values and the NULL LAST option places NULL after other non-null values.
-   Let’s create a table for the demonstration.

![](media/3c314c99c6e8f3ffb82d260a03f93485.png)

-   The following query returns data from the sort_demo table:

![](media/842313b078d1ad6fdc7e05f92f212274.png)

**Output**

![](media/a41e8f4877dfb7754a44481cb1a24d84.png)

-   In this example, the ORDER BY clause sorts values in the num column of the sort_demo table in ascending order. It places NULL after other values.
-   So if you use the ASC option, the ORDER BY clause uses the NULLS LAST option by default. Therefore, the following query returns the same result:

![](media/42acd7e03e7c28e7d1a1edc2586ef84a.png)

-   To place NULL before other non-null values, you use the NULLS FIRST option:

![](media/32b95bb445d24aa7079915a757282e1e.png)

**Output**

![](media/162716ab20b67ad2b0000a5c7c0ac697.png)

-   The following statement sorts values in the num column of the sort_demo table in descending order:

![](media/b51c43b03e539093015ffc0394b65749.png)

**Output**

![](media/8be124817b554e1cbaa7f957c1378cc7.png)

-   As you can see clearly from the output, the ORDER BY clause with the DESC option uses the NULLS FIRST by default.
-   To reverse the order, you can use the NULLS LAST option:

![](media/407f499d914209f69dba03098706ed44.png)

**Output**

![](media/5a58e3501ffd6999c7f159acc7637012.png)

## 5. PostgreSQL WHERE Clause

-   The syntax of the PostgreSQL WHERE clause is as follows:

![](media/380ff90070a69964d19b609a351bf090.png)

-   The WHERE clause appears right after the FROM clause of the SELECT statement. The WHERE clause uses the condition to filter the rows returned from the SELECT clause.
-   The condition must evaluate to true, false, or unknown. It can be a boolean expression or a combination of boolean expressions using the AND and OR operators.
-   The query returns only rows that satisfy the condition in the WHERE clause. In other words, only rows that cause the condition evaluates to true will be included in the result set.
-   PostgreSQL evaluates the WHERE clause after the FROM clause and before the SELECT and ORDER BY clause:

![](media/decae53de6821081df5565d222a15b75.png)

-   If you use column aliases in the SELECT clause, you cannot use them in the WHERE clause.
-   Besides the SELECT statement, you can use the WHERE clause in the UPDATE and DELETE statement to specify rows to be updated or deleted.
-   To form the condition in the WHERE clause, you use comparison and logical operators:

![](media/f2885115cd6f3ee70a4c4a5448c9b07e.png)

## 5.1 PostgreSQL WHERE Clause Examples

-   We will use the **customer table** from the sample database for demonstration.

![](media/e38b655f74cfc39d92bf793fd23ec56c.png)

## 1) Using WHERE clause with the equal (=) operator

-   The following statement uses the WHERE clause customers whose first names are Jamie:

![](media/452a20b235bd8f215a1584daae5e9323.png)

**Output**

![](media/c88e0cac00a1200a38ab316d6effcb41.png)

## 2) Using WHERE clause with the AND operator

-   The following example finds customers whose first name and last name are Jamie and rice by using the AND logical operator to combine two Boolean expressions:

![](media/524cc0eab1e7e674f24c9a14ba15057c.png)

**Output**

![](media/23cbca74df30fbcea4fdcff5b735c196.png)

## 3) Using the WHERE clause with the OR operator

-   This example finds the customers whose last name is Rodriguez or first name is Adam by using the OR operator:

![](media/96cccdb567d5bd6309d397bf10c68bd2.png)

**Output**

![](media/0f71d65d184cfe2bbe11fbebcd61196b.png)

## 4) Using WHERE clause with the IN operator

-   If you want to match a string with any string in a list, you can use the IN operator.
-   For example, the following statement returns customers whose first name is Ann, or Anne, or Annie:

![](media/a8ced5ae43540a38988ef854d05b3292.png)

**Output**

![](media/7cc3ce65ab275c4d377583fd9a1bb2ea.png)

## 5) Using the WHERE clause with the LIKE operator

-   To find a string that matches a specified pattern, you use the LIKE operator.
-   The following example returns all customers whose first names start with the string Ann:

![](media/b31c7ff01e98e6bd6e233ebd26bf0004.png)

**Output**

![](media/ed8c082a8d2dc889318ff4a61123be07.png)

-   The **%** is called a **wildcard** that matches any string. The 'Ann%' pattern matches any string that starts with 'Ann'.

## 6) Using the WHERE clause with the BETWEEN operator

-   The following example finds customers whose first names start with the letter A and contains 3 to 5 characters by using the BETWEEN operator.
-   The BETWEEN operator returns true if a value is in a range of values.

![](media/fd6624b149363edb3a001a9087ea52c3.png)

**Output**

![](media/95ea268cae5574dbd17b86446767be0f.png)

-   In this example, we used the LENGTH() function gets the number of characters of an input string.

## 7) Using the WHERE clause with the not equal operator (\<\>)

-   This example finds customers whose first names start with Bra and last names are not Motley:

![](media/e11de27399766bffeb211eb5e818e2fa.png)

**Output**

![](media/d2b138047ba5e46d3bcc8580170e8435.png)

-   **Note that** you can use the **!=** operator and **\<\>** operator interchangeably because they are equivalent.

## 6. PostgreSQL GROUP BY Clause

-   The GROUP BY clause divides the rows returned from the SELECT statement into groups. For each group, you can apply an aggregate function e.g., SUM() to calculate the sum of items or COUNT() to get the number of items in the groups.
-   The following statement illustrates the basic syntax of the GROUP BY clause:

![](media/202448da8b701138dcacd186b3f95ffc.png)

In this syntax:

-   **First,** select the columns that you want to group e.g., column1 and column2, and column that you want to apply an aggregate function (column3).
-   **Second**, **list the columns** that you want to **group** in the GROUP BY clause.

The statement clause divides the rows by the values of the columns specified in the GROUP BY clause and calculates a value for each group.

-   It’s possible to use other clauses of the SELECT statement with the GROUP BY clause.
-   PostgreSQL evaluates the GROUP BY clause after the FROM and WHERE clauses and before the HAVING, SELECT, DISTINCT, ORDER BY and LIMIT clauses.

![](media/90e8f30923b4fa3706cf30ac290d85a5.png)

## 6.1 PostgreSQL GROUP BY clause Examples

-   Let’s take a look at the **payment** table in the sample database.

![](media/19b448768689fbc53d60aac1973e4a28.png)

## 1) Using PostgreSQL GROUP BY without an aggregate Function

-   You can use the GROUP BY clause without applying an aggregate function.
-   The following query gets data from the payment table and groups the result by customer id.

![](media/d8ae2b79617fe383b1493a3424048ada.png)

**Output**

![](media/44d3df913f22997b692eec35c617c6a1.png)

-   In this case, the GROUP BY works like the DISTINCT clause that removes duplicate rows from the result set.

## 2) Using PostgreSQL GROUP BY with SUM() Function

-   The GROUP BY clause is useful when it is used in conjunction with an aggregate function.
-   For example, to select the total amount that each customer has been paid, you use the GROUP BY clause to divide the rows in the payment table into groups grouped by customer id. For each group, you calculate the total amounts using the SUM() function.
-   The following query uses the GROUP BY clause to get total amount that each customer has been paid:

![](media/986986749eb66ed35167642c7d287d83.png)

**Output**

![](media/18616e8077c17c3c39191b1fde6f9d8b.png)

-   The GROUP BY clause sorts the result set by customer id and adds up the amount that belongs to the same customer. Whenever the customer_id changes, it adds the row to the returned result set.
-   The following statement uses the ORDER BY clause with GROUP BY clause to sort the groups:

![](media/8665d8472737c9a9988e59c69227c5b3.png)

**Output**

![](media/dfa26102659d4008287d2efd36701492.png)

## 3) Using PostgreSQL GROUP BY clause with the JOIN Clause

-   The following statement uses the GROUP BY clause with the INNER JOIN clause the get the total amount paid by each customer.

Unlike the previous example, this query joins the payment table with the customer table and group customers by their names.

![](media/e05c252382cd743c4b3454a6dbf5198c.png)

**Output**

![](media/be6a564cae14dae20bd3ed861fbb0e00.png)

## 4) Using PostgreSQL GROUP BY with COUNT() Function

-   To find the number of payment transactions that each staff has been processed, you group the rows in the payment table by the values in the staff_id column and use the COUNT() function to get the number of transactions

![](media/c348be618f78466dc3e5c9c38e8069fc.png)

**Output**

![](media/c49af7885f17d89c8f9c7f3f700a1db1.png)

-   The GROUP BY clause divides the rows in the payment into groups and groups them by value in the staff_id column. For each group, it returns the number of rows by using the COUNT() function.

## 5) Using PostgreSQL GROUP BY with multiple columns

-   The following example uses multiple columns in the GROUP BY clause

![](media/11ed48237dadc2d843acfa7f2872986c.png)

-   In this example, the GROUP BY clause divides the rows in the payment table by the values in the customer_id and staff_id columns. For each group of (customer_id, staff_id), the SUM() calculates the total amount.

**Output**

![](media/0d62ef762bcaf93a591c10b79438b223.png)

## 6) Using PostgreSQL GROUP BY clause with date column

-   The payment_date is a timestamp column. To group payments by dates, you use the DATE() function to convert timestamps to dates first and then group payments by the result date:

![](media/66e376d107ec7ba33be8a49bfc6afcb5.png)

**Output**

![](media/826b10c4e2fba22af521695e6ed7534b.png)

## 7. PostgreSQL HAVING Clause

-   The HAVING clause specifies a search condition for a group or an aggregate.
-   The HAVING clause is often used with the GROUP BY clause to filter groups or aggregates based on a specified condition.
-   The following statement illustrates the basic syntax of the HAVINGclause:

![](media/576c1821e2a08cf70fd889448ada018b.png)

-   In this syntax, the group by clause returns rows grouped by the column1. The HAVING clause specifies a condition to filter the groups.
-   It’s possible to add other clauses of the SELECT statement such as JOIN, LIMIT, FETCH etc.
-   PostgreSQL evaluates the HAVING clause after the FROM, WHERE, GROUP BY, and before the SELECT, DISTINCT, ORDER BY and LIMIT clauses.

![](media/a49507b9830ce2856554323ca7fe177f.png)

-   Since the HAVING clause is evaluated before the SELECT clause, you cannot use column aliases in the HAVING clause. Because at the time of evaluating the HAVING clause, the column aliases specified in the SELECT clause are not available.

## 7.1 HAVING vs. WHERE

-   The WHERE clause allows you to filter rows based on a specified condition. However, the HAVING clause allows you to filter groups of rows according to a specified condition.
-   In other words, the WHERE clause is applied to rows while the HAVING clause is applied to groups of rows.

## 7.2 PostgreSQL HAVING Clause Examples

-   Let’s take a look at the **payment** table in the sample database.

![](media/00241351ec3f3ca0d692b82b3baf2c65.png)

## 1) Using PostgreSQL HAVING clause with SUM function example

-   The following query uses the GROUP BY clause with the SUM() function to find the total amount of each customer:

![](media/937e7e3a8ffd7201a05ceddec8867a7a.png)

**Output**

![](media/4de64a10f3c27d2d7eead3f3f888a8ae.png)

-   The following statement adds the HAVING clause to select the only customers who have been spending more than 200:

![](media/a64574c5d6d74aa1bc4e02b2e4e5025c.png)

**Output**

![](media/527dae1aa7d73d7f045a8d834f68d224.png)

## 2) PostgreSQL HAVING clause with COUNT example

-   See the following **customer** table from the sample database:

![](media/bbccc3d412642e783acff704e30b7bb1.png)

-   The following query uses the GROUP BY clause to find the number of customers per store:

![](media/9a5d260bbc44b3e330458de8dfc8b083.png)

**Output**

![](media/cb060eb5013d29a024bfcc94397f454c.png)

-   The following statement adds the HAVING clause to select the store that has more than 300 customers:

![](media/349e3fcf043ac216018204886bb85128.png)

**Output**

![](media/c481b7703cb826df590521e54d663cb3.png)

## 8. References

1.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-select/
2.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-order-by/
3.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-where/
4.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-group-by/
5.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-having/
