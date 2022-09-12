## Joins

**Content**

1\. PostgreSQL Joins

1.2 Sample tables

2\. PostgreSQL inner join

3\. PostgreSQL left join

4\. PostgreSQL right join

5\. PostgreSQL full outer join/ full join

6\. References

## 1. PostgreSQL Joins

-   PostgreSQL join is used to combine columns from one (self-join) or more tables based on the values of the common columns between related tables.
-   The common columns are typically the primary key columns of the first table and foreign key columns of the second table.
-   PostgreSQL supports inner join, left join, right join, full outer join, cross join, natural join, and a special kind of join called self-join.

## 1.2 Sample tables

-   Suppose you have two tables called **basket_a** and **basket_b** that store fruits:

![](media/ae0a60c07b2539e4b377bb9f5210a6fe.png)

-   The tables have some common fruits such as **apple** and **orange.**
-   The following statement returns data from the **basket_a** table:

![](media/727eeee5a19e13f20ff30cec907e6416.png)

-   And the following statement returns data from the **basket_b** table:

![](media/95e975981f831f09f51d6b797fedfcc5.png)

## 2. PostgreSQL inner join

-   The following statement joins the first table (**basket_a**) with the second table (**basket_b**) by matching the values in the **fruit_a** and **fruit_b** columns:

![](media/ca838a09984264ca11302c369dcbe6b3.png)

**Output**

![](media/961bfd242338a0886ffe9fce90ae8168.png)

-   The inner join examines each row in the first table (basket_a).
-   It compares the value in the fruit_a column with the value in the fruit_b column of each row in the second table (basket_b).
-   If these values are equal, the inner join creates a new row that contains columns from both tables and adds this new row the result set.
-   The following Venn diagram illustrates the inner join:

![](media/a9c542b319eb9884c6b433b2131a6e26.png)

## 3. PostgreSQL left join

-   The following statement uses the left join clause to join the basket_a table with the basket_b table.
-   In the left join context, the first table is called the left table and the second table is called the right table.

![](media/be80bf3873883ad195cb731903d0c2be.png)

**Output**

![](media/b0bcc5d34fa8e805a671b5ef77104b50.png)

-   The left join starts selecting data from the left table.
-   It compares values in the fruit_a column with the values in the fruit_b column in the basket_b table.
-   If these values are equal, the left join creates a new row that contains columns of both tables and adds this new row to the result set. (see the row \#1 and \#2 in the result set).
-   In case the values do not equal, the left join also creates a new row that contains columns from both tables and adds it to the result set. However, it fills the columns of the right table (basket_b) with null. (see the row \#3 and \#4 in the result set).
-   The following Venn diagram illustrates the left join:

![](media/c5890a8c651000e4343a42f6f8ba664b.png)

-   To select rows from the left table that do not have matching rows in the right table, you use the left join with a **WHERE** clause. For example:

![](media/d542d920c35cec683bc2fa2d51628d50.png)

**Output**

![](media/54cf7067f0dd91e1d27e379a11f36d35.png)

![](media/5eedbb4b5d306072042b9c38d3d9f0a3.png)

-   The following Venn diagram illustrates the left join that returns rows from the left table that do not have matching rows from the right table:

![](media/5bea0679b1093c25e1399146cd83d205.png)

## 4. PostgreSQL right join

-   The right join is a reversed version of the left join.
-   The right join starts selecting data from the right table. It compares each value in the fruit_b column of every row in the right table with each value in the fruit_a column of every row in the fruit_a table.
-   If these values are equal, the right join creates a new row that contains columns from both tables.
-   In case these values are not equal, the right join also creates a new row that contains columns from both tables. However, it fills the columns in the left table with NULL.
-   The following statement uses the right join to join the basket_a table with the basket_b table:

![](media/67bbffe7d568f4fc0de4d196459c970e.png)

**Output**

![](media/0ab8329a808890aee7d51a3f93c75279.png)

-   The following Venn diagram illustrates the right join:

![](media/bf2e43d9d82c60e0d68fd1ba25a17552.png)

-   Similarly, you can get rows from the right table that do not have matching rows from the left table by adding a WHERE clause as follows:

![](media/8f04e4f841c7d9fde5b643e9c9416da7.png)

**Output**

![](media/ce294b96167e8ca026edc7d683684701.png)

![](media/4890fe4783e3f5aa63fd9800422a8b8a.png)

-   The following Venn diagram illustrates the right join that returns rows from the right table that do not have matching rows in the left table:

![](media/6d49df8907b4532dfa55498e574ec65b.png)

## 5. PostgreSQL full outer join/ full join

-   The **full outer join or full join** returns a result set that contains all rows from both left and right tables, with the matching rows from both sides if available.
-   In case there is no match, the columns of the table will be filled with NULL.

![](media/67a28139580c7936968f8214e2a81996.png)

**Output:**

![](media/887be3a40e71fef547206f78f88ba3eb.png)

-   The following Venn diagram illustrates the full outer join:

![](media/ea4c6cf79255676c4a0a29cf3085fbd2.png)

-   To return rows in a table that do not have matching rows in the other, you use the full join with a WHERE clause like this:

![](media/1d8fa84f71d3706f37c5462619c091bf.png)

**Output**

![](media/1461ea1336ef95782ab6c8e196546311.png)

-   The following Venn diagram illustrates the full outer join that returns rows from a table that do not have the corresponding rows in the other table:

![](media/0862b49c8b5d3d64ca7febbbb86b0b29.png)

-   The following picture shows all the PostgreSQL joins that we discussed so far with the detailed syntax:

## ![](media/db3b5d86024854ff564670e7285d4e33.png)

## 6. References

https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-joins/
