## Primary key

**Content**

**1. Primary key**

1.1 Define primary key when creating the table

1.2 Define primary key when changing the existing table structure

1.3 How to add an auto-incremented primary key to an existing table

1.4 Remove primary key

**2. References**

## 1. Primary key

-   A primary key is a column or a group of columns used to identify a row uniquely in a table.
-   Primary key constraint is the combination of a not-null constraint and a UNIQUE constraint.
-   A table can have one and only one primary key. It is a good practice to add a primary key to every table.

## 1.1 Define primary key when creating the table

-   Normally, we add the primary key to a table when we define the table’s structure using **CREATE TABLE** statement.

![](media/eb7cd7de58e32d25721128d712e529d3.png)

-   In case the primary key consists of two or more columns, you define the primary key constraint as follows:

![](media/4442b7db4329e5d291bf1a8edb519479.png)

**Example**

![](media/3c88ea1340f6085a10173109fc24fff1.png)

-   If you don’t specify explicitly the name for primary key constraint, PostgreSQL will assign a default name to the primary key constraint.
-   By default, PostgreSQL uses **table-name_pkey** as the default name for the primary key constraint.
-   In the above example, PostgreSQL creates the primary key constraint with the name **po_items_pkey** for the po_items table.

In case you want to specify the name of the primary key constraint, you use CONSTRAINT clause as follows:

![](media/f9ce8649a4dc9a35f26fe2af5e5adac4.png)

## 1.2 Define primary key when changing the existing table structure

-   It is rare to define a primary key for existing table. In case you have to do it, you can use the **ALTER** **TABLE** statement to add a primary key constraint.

![](media/c1a1cb2f7591c1a42bdf615d8468b45e.png)

**Example**

-   Creates a table named **products** without defining any primary key.

![](media/f50c7e6bb01d659004cc5107e50d6145.png)

-   Suppose you want to add a primary key constraint to the products table, you can execute the following statement:

![](media/0d40a408eee603ec6e7be9a32ab26916.png)

## 1.3 How to add an auto-incremented primary key to an existing table

-   Suppose, we have a **vendors** table that does not have any primary key.

![](media/90a81db53ea837356463a01106f7bdb6.png)

-   And we add few rows to the **vendors** table using **INSERT** statement:

![](media/8460c4acacdef17044853bb7850335c9.png)

-   To verify the insert operation, we query data from the vendors table using the following **SELECT** statement:

![](media/82e682b15b6a21f8eca8f8f0ee38c69a.png)

-   Now, if we want to add a primary key named **id** into the **vendors** table and the **id** field is auto-incremented by one, we use the following statement:

![](media/f2fdd14470bead0c01da1bd95731f71c.png)

-   Let’s check the vendors table again.

![](media/8df3e4dfa7ec63be963c8a9b584da4e6.png)

## 1.4 Remove primary key

-   To remove an existing primary key constraint, you also use the **ALTER TABLE** statement with the following syntax:

![](media/6a8c1543053c1a95d1ed2c5d4b004ea1.png)

-   For example, to remove the primary key constraint of the products table, you use the following statement:

![](media/e6edf81f62c2710cf2178eb6a8968e60.png)

## 2. References

-   https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-primary-key/
