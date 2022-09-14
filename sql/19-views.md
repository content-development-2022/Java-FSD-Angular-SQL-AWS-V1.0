# VIEWS

**Content**

1\. PostgreSQL Views

2\. Creating PostgreSQL Views

2.1 PostgreSQL View with Select Statement Example

3\. Changing PostgreSQL Views

4\. Removing PostgreSQL Views

5\. References

## 1. PostgreSQL Views

-   A view is a database object that is of a stored query.
-   A view can be accessed as a virtual table in PostgreSQL. In other words, a PostgreSQL view is a logical table that represents data of one or more underlying tables through a SELECT statement.
-   Notice that a view does not store data physically except for a materialized view.

![](media/6801e93b7f744abf2b277642099eac69.png)

A view can be very useful in some cases such as:

-   A view helps simplify the complexity of a query because you can query a view, which is based on a complex query, using a simple SELECT statement.
-   Like a table, you can grant permission to users through a view that contains specific data that the users are authorized to see.
-   A view provides a consistent layer even the columns of underlying table changes.

## 2. Creating PostgreSQL Views

-   To create a view, we use CREATE VIEW statement.
-   The simplest syntax of the CREATE VIEW statement is as follows:

![](media/a000fafa6b1ec6b7b3aa814789f96174.png)

-   **First,** you specify the **name** of the **view** after the CREATE VIEW clause, then you put a **query after the AS** keyword.
-   A query can be a simple SELECT statement or a complex SELECT statement with joins.

## 2.1 PostgreSQL View with Select Statement Example

For example, in our sample database, we have four tables:

1.  customer – stores all customer data
2.  address – stores address of customers
3.  city – stores city data
4.  country– stores country data

![](media/cc043d2aa6ea0007fe711e21a5e2359e.png)

-   If you want to get a complete customers data, you normally construct a join statement as follows:

![](media/a05896dc5c84b790aa8a3c16acf47ad9.png)

-   The result of the query is as shown in the screenshot below:

![](media/be6586f3255ce88d47f0914e103541ac.png)

-   This query is quite complex. However, you can create a view named customer_master as follows:

![](media/1784cf98d6ec3b066a4ce79b6518aee6.png)

-   From now on, whenever you need to get a complete customer data, you just query it from the view by executing the following simple SELECT statement:

![](media/3fe35a555de69540b6aa7023583886e8.png)

-   This query produces the same result as the complex one with joins above.

## 3. Changing PostgreSQL Views

-   To change the defining query of a view, you use the CREATE VIEW statement with OR REPLACE addition as follows:

![](media/e64334081f755aac3278cf445495b609.png)

-   PostgreSQL does not support removing an existing column in the view, at least up to version 9.4.
-   If you try to do it, you will get an error message:

    “[Err] ERROR: cannot drop columns from view”.

-   The query must generate the same columns that were generated when the view was created.
-   To be more specific, the new columns must have the same names, same data types, and in the same order as they were created.
-   However, PostgreSQL allows you to append additional columns at the end of the column list.

For example, you can add an email to the customer_master view as follows:

![](media/314a6b78c72e5dfe386bfcd564e10de2.png)

-   Now, if you select data from the customer_master view, you will see the email column at the end of the list.

![](media/5a8ef5673c64929862d107fc9b37b384.png)

![](media/af4dce2aa2cbc3aee229bb8f1a44cc49.png)

-   To change the definition of a view, you use the ALTER VIEW statement.
-   For example, you can change the name of the view from customer_master to customer_info by using the following statement:

![](media/5ca7ea862ede9800acec74a90511c52b.png)

## 4. Removing PostgreSQL Views

-   To remove an existing view in PostgreSQL, you use DROP VIEW statement as follows:

![](media/77fa73972489c3a84a040bb2e545d19c.png)

-   You specify the name of the view that you want to remove after DROP VIEW clause.
-   Removing a view that does not exist in the database will result in an error. To avoid this, you normally add IF EXISTS option to the statement to instruct PostgreSQL to remove the view if it exists, otherwise, do nothing.
-   For example, to remove the customer_info view that you have created, you execute the following query:

![](media/50f3db88a52ce7eb48defa03c83eadbd.png)

-   The view customer_info is removed from the database.

## 5. References

1.  https://www.postgresqltutorial.com/postgresql-views/
2.  https://www.postgresqltutorial.com/postgresql-views/managing-postgresql-views/
