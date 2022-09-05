# SQL Constraints

**Content**

**1. SQL Constraints**

**1.1 PostgreSQL NOT NULL Constraint**

1.1.1 SQL NOT NULL on CREATE TABLE

1.1.2 Adding NOT NULL Constraint to Existing Columns

1.1.3 The Special Case of NOT NULL Constraint

**1.2 PostgreSQL UNIQUE Constraint**

1.2.1 PostgreSQL UNIQUE Constraint Example

1.2.2 Creating a UNIQUE Constraint on Multiple Columns

1.2.3 Adding Unique Constraint Using a Unique Index

**1.3 PostgreSQL CHECK Constraint**

1.3.1 Define PostgreSQL CHECK Constraint for New Tables

1.3.1 Define PostgreSQL CHECK constraints for existing tables

**2. References**

# 1. SQL Constraints

-   SQL constraints are used to specify **rules for data in a table.**
-   Constraints are used to limit the type of data that can go into a table.
-   This ensures the accuracy and reliability of the data in the table.
-   If there is any violation between the constraint and the data action, the action is aborted.
-   Constraints can be column level or table level. Column level constraints apply to a column, and table level constraints apply to the whole table.

The following constraints are commonly used in SQL:

-   **NOT NULL** - Ensures that a column cannot have a NULL value
-   **UNIQUE** - Ensures that all values in a column are different
-   **PRIMARY KEY** - A combination of a **NOT NULL** and **UNIQUE**. Uniquely identifies each row in a table
-   **FOREIGN KEY** - Prevents actions that would destroy links between tables
-   **CHECK** - Ensures that the values in a column satisfies a specific condition

## 1.1 PostgreSQL NOT NULL Constraint

-   By default, a column can hold NULL values.
-   The **NOT NULL** constraint enforces a column to **NOT accept NULL values.**
-   This enforces a field to always contain a value, which means that you cannot insert a new record, or update a record without adding a value to this field.

## 1.1.1 SQL NOT NULL on CREATE TABLE

![](media/8c6b5c215e0c1459ff6eaf17c6942828.png)

## 1.1.2 Adding NOT NULL Constraint to Existing Columns

-   To add the NOT NULL constraint to a column of an existing table, you use the following form of the **ALTER TABLE** statement:

![](media/8bbe84f3bae4fe257c7d0f9db25993e3.png)

-   To add set **multiple NOT NULL** constraint to multiple columns, you use the following syntax:

![](media/43d60952f02a368af32ae14693ae49ba.png)

**Example**

-   First, create a new table called **production orders** ( production_orders):

![](media/58df5b7ab338cd43b9dcb0d634b499b4.png)

-   Next, **insert a new row** into the production_orders table:

![](media/18049ecd58dace7be38604dff018675f.png)

-   Then, to make sure that the **qty** field is not null, you can add the not-null constraint to the **qty** column. However, the column already contains data. If you try to add the not-null constraint, **PostgreSQL will issue an error**.
-   To add the NOT NULL constraint to a column that already contains NULL, you need to update NULL to non-NULL first, like this:

![](media/26f65cec8975a2cb0a435f89ec0b2e42.png)

-   The values in the qty column are updated to one. Now, you can add the NOT NULL constraint to the qty column:

![](media/f7742c03869df66541561be2b894051b.png)

-   After that, you can update the not-null constraints for material_id, start_date, and finish_date columns:

![](media/a6ef0b07723046fec83378624aee2b42.png)

-   Add not-null constraints to multiple columns:

![](media/ab21f4c92ada63e79834986642ef618f.png)

-   Finally, attempt to update values in the qty column to NULL:

![](media/88fe8a95bd12daa46939c2066cd56ad2.png)

-   PostgreSQL issued an error message:

![](media/c4c7c8e8d2d1018c00154265bbcff739.png)

## 1.1.3 The Special Case of NOT NULL Constraint

-   Besides the NOT NULL constraint, you can use a CHECK constraint to force a column to accept not NULL values.
-   The NOT NULL constraint is equivalent to the following CHECK constraint:

![](media/97de97596d0eec32232dce342467190c.png)

-   By default, PostgreSQL gives the CHECK constraint name using the following pattern:

![](media/1784912d0702fae2ca82882fb9209ff2.png)

-   However, if you want to assign a CHECK constraint a specific name, you can specify it after the CONSTRAINT expression. In the below example **username**
-   **\_email_notnull** is check constraint name.
-   This is useful because sometimes you may want either column a or b is not null, but not both.
-   For example, you may want either username or email column of the user tables is not null or empty. In this case, you can use the CHECK constraint as follows:

![](media/53734ab40acc5227f0a55633d5af3a1f.png)

-   The following statement works.

![](media/2d15a2821dc9c85f372783264176f167.png)

-   However, the following statement will not work because it violates the CHECK constraint:

![](media/13ba682eb4fdf72dacb64b6912960e62.png)

## Note

-   Use the NOT NULL constraint for a column to enforce a column not accept NULL. By default, a column can hold NULL.
-   To check if a value is NULL or not, you use the IS NULL operator. The IS NOT NULL negates the result of the IS NULL.
-   Never use equal operator = to compare a value with NULL because it always returns NULL.

# 1.2 PostgreSQL UNIQUE Constraint

-   UNIQUE constraint to make sure that values stored in a column or a group of columns are unique across rows in a table.
-   Sometimes, you want to ensure that values stored in a column or a group of columns are unique across the whole table such as email addresses or usernames.
-   PostgreSQL provides you with the UNIQUE constraint that maintains the uniqueness of the data correctly.
-   When a UNIQUE constraint is in place, every time you insert a new row, it checks if the value is already in the table. It rejects the change and issues an error if the value already exists. The same process is carried out for updating existing data.
-   When you add a UNIQUE constraint to a column or a group of columns, PostgreSQL will automatically create a unique index on the column or the group of columns.

## 1.2.1 PostgreSQL UNIQUE Constraint Example

-   The following statement creates a new table named **person** with a UNIQUE constraint for the email column.

![](media/d593fdc89cea6575669efba03b31da88.png)

-   **Note** that the UNIQUE constraint above can be **rewritten as a table constraint** as shown in the following query:

![](media/bbc8bab65145430f30085a72979881b6.png)

-   First, insert a new row into the person table using INSERT statement:

![](media/b3db6e94e26d2d94e2b0c17534e0dd57.png)

-   Second, insert another row with duplicate email.

![](media/370886c1c58d9dddf0a7a4227a9b314d.png)

-   PostgreSQL issued an error message.

![](media/ef45dbc8de1dd6f45ac879b3450c67cb.png)

## 1.2.2 Creating a UNIQUE Constraint on Multiple Columns

-   PostgreSQL allows you to create a UNIQUE constraint to a group of columns using the following syntax:

![](media/ef5c8b821b49402f0c8904990c84d5a6.png)

-   The combination of values in column c2 and c3 will be unique across the whole table.
-   The value of the column c2 or c3 needs not to be unique.

## 1.2.3 Adding Unique Constraint Using a Unique Index

-   Sometimes, you may want to add a unique constraint to an existing column or group of columns. Let’s take a look at the following example.
-   First, suppose you have a table named **equipment**:

![](media/5a7a19ce6856be760cc1190484e3570c.png)

-   Second, create a **unique index** based on the **equip_id** column.

![](media/3c0f66bc55c0e33c377d6e5a1ea08692.png)

-   Third, add a **unique constraint** to the equipment table using the **equipment_equip_id index.**

![](media/dcfba087a083898a410ef5a62dfd69ee.png)

-   Notice that the ALTER TABLE statement acquires an exclusive **lock** on the table. If you have **any pending transactions**, it will **wait** for **all transactions to complete** before changing the table.
-   Therefore, you should check the **pg_stat_activity** table to see the current pending transactions that are on-going using the following query:

![](media/b5eddf08020a643e54b1e56cada6189d.png)

-   You should look at the result to find the state column with the value idle in transaction. Those are the transactions that are pending to complete.

# 1.3 PostgreSQL CHECK Constraint

-   A CHECK constraint is a kind of constraint that **allows you to specify if values in a column must meet a specific requirement.**
-   The CHECK constraint uses a **Boolean expression** to evaluate the values before they are inserted or updated to the column.
-   If the values pass the check, PostgreSQL will insert or update these values to the column. Otherwise, PostgreSQL will reject the changes and issue a constraint violation error.

## 1.3.1 Define PostgreSQL CHECK Constraint for New Tables

-   Typically, you use the CHECK constraint at the time of creating the table using the **CREATE TABLE** statement.
-   The following statement defines an **employees** table.

![](media/c6535cc76f6bfb9c0bcbaea8dfe5bbb6.png)

The employees table has three CHECK constraints:

1.  First, the **birth date** ( birth_date) of the employee must be greater than 01/01/1900. If you try to insert a birth date before 01/01/1900, you will receive an error message.
2.  Second, the **joined date** ( joined_date) must be greater than the birth date ( birth_date). This check will prevent from updating invalid dates in terms of their semantic meanings.
3.  Third, the **salary** must be greater than zero, which is obvious.
-   Let’s try to insert a **new row** into the employees table:

![](media/bef90836299d708a6ba15f1bc7115890.png)

-   The statement attempted to insert a negative salary into the salary column. However, PostgreSQL returned the following error message:

![](media/3a2bd5cb7030e9dbe430949f4ef06275.png)

-   The insert failed because of the CHECK constraint on the salary column that accepts only positive values.
-   By default, PostgreSQL gives the CHECK constraint a name using the following pattern:

![](media/1784912d0702fae2ca82882fb9209ff2.png)

-   For example, the constraint on the salary column has the following constraint name:

![](media/f43d0a21757fcf366c1c7ae0a09e902c.png)

-   However, if you want to assign aCHECK constraint a specific name, you can specify it after the CONSTRAINT expression as follows:

![](media/efe9a664ca7860cb4136e9dce4bc3bc1.png)

-   See the following example:

![](media/feba0fdba2f0f91849ecb27a50fb1a65.png)

## 1.3.1 Define PostgreSQL CHECK constraints for existing tables

-   To add CHECK constraints to existing tables, you use the **ALTER TABLE** statement.
-   Suppose, you have an existing table in the database named **prices_list**

![](media/21474ad2315cbd972be0bf217714cd0f.png)

-   Now, you can use ALTER TABLE statement to add the CHECK constraints to the prices_list table. The price and discount must be greater than zero and the discount is less than the price. Notice that we use a **Boolean expression** that contains the **AND** operators.

![](media/6c36fd41096893eeef5cf888f3813499.png)

-   The valid to date ( valid_to) must be greater than or equal to valid from date ( valid_from).

![](media/045ea846423ad93b7021a6eb0237b18c.png)

-   The CHECK constraints are very useful to place additional logic to restrict values that the columns can accept at the database layer. By using the CHECK constraint, you can make sure that data is updated to the database correctly.

## 2. References

1.  https://www.w3schools.com/sql/sql_constraints.asp
2.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-unique-constraint/
3.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-not-null-constraint/
4.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-check-constraint/
