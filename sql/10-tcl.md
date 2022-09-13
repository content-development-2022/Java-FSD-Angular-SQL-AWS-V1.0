## Transaction Control Languages

**Contents**

1\. Transaction Control Languages

1.1 What is a database transaction

2\. PostgreSQL Transaction Statements

2.1 Begin a Transaction

2.2 Commit a Transaction

2.2.1 PostgreSQL COMMIT: Bank account transfer example

2.3 Rolling back a Transaction

2.4 Savepoint a Transaction

2.5 Savepoint Examples

3\. References

## 1. Transaction Control Languages

-   **TCL** stands for **Transaction Control Languages**.
-   A **Transaction** is a set of SQL statements that are executed on the data stored in DBMS. Whenever any transaction is made the transactions are temporarily happen in database. So to make the changes permanent, we use **TCL** commands.
-   TCL commands are: Begin, Commit, Rollback, Savepoint.

## 1.1 What is a database transaction

-   A database transaction is a single unit of work that consists of one or more operations.
-   A classical example of a transaction is a bank transfer from one account to another.
-   A complete transaction must ensure a balance between the sender and receiver accounts. It means that if the sender account transfers X amount, the receiver receives X amount, no more or no less.

A PostgreSQL transaction is **atomic, consistent, isolated, and durable**. These properties are often referred to as **ACID**:

-   **Atomicity** guarantees that the transaction completes in an all-or-nothing manner.
-   **Consistency** ensures the change to data written to the database must be valid and follow predefined rules.
-   **Isolation** determines how transaction integrity is visible to other transactions.
-   **Durability** makes sure that transactions that have been committed will be stored in the database permanently.

## 2. PostgreSQL Transaction Statements

Below is the transaction statements which was used in PostgreSQL.

-   Begin
-   Commit
-   Rollback
-   Savepoint

## 2.1 Begin a Transaction

-   Begin statement is a transaction statement used to start a new transaction.
-   To start a new transaction, we have using begin statements in PostgreSQL.
-   Let’s create a new table named **accounts** for the demonstration:

![](media/cdbafda33096cf5c6d51fab08700eb17.png)

-   When you execute the following INSERT statement:

![](media/2d473a2f2763414f9d42124bfea8e0c2.png)

-   PostgreSQL inserted a new row into the accounts table immediately. In this case, you do not know when the transaction begins and cannot intercept the modification such as rolling it back.
-   To start a transaction, you use the below syntax for begin statement:

![](media/b386e13c5a11df06f146dfd4c4b01df5.png)

Or

![](media/e3ea17e1659fe0fb8df20fc268c9c046.png)

or just:

![](media/d02286f0d00d171c9b0bcbba8e8e87a4.png)

-   For example, the following statements start a new transaction and insert a new account into the accounts table:

![](media/54190a43a3847bbe003dc4fda1246606.png)

-   From the current session, you can see the change by querying the accounts table:

![](media/c56d5f088e8370aa3f5b31a04d12caac.png)

**Output**

![](media/ef4d383b6ad7b501bd8f252eab558aba.png)

## 2.2 Commit a Transaction

-   Commit command in PostgreSQL is very important to save the transaction into the database server.
-   To make the change become visible to other sessions (or users) you need to commit the transaction by using the COMMIT WORK statement:
-   Below is the syntax for the Commit statement in PostgreSQL.

![](media/ed6d4e82d7d1a7e4289e31c5a605e456.png)

Or

![](media/185a6d227e6e60e16d6e63f363c92a23.png)

or simply:

![](media/21e2909514785eab69fe2a4a3810b6db.png)

-   The following COMMIT statement inserts Alice’s account to the accounts table:

![](media/abcb9a55f8a26612bc880eb337c732f6.png)

-   From other sessions, you can view the change by querying the accounts table:

![](media/4966a4d2f0948ede41ee2986cfcd8be9.png)

**Output**

![](media/86c4e914589f9e5a5397a913771d9b3f.png)

-   After executing the COMMIT statement, PostgreSQL also guarantees that the change will be durable if a crash happens.
-   Put it all together.

![](media/8c224724680be82761477c130add5b48.png)

## 2.2.1 PostgreSQL COMMIT: Bank account transfer example

-   In this demonstration, we will show you how to transfer 1000USD from Bob’s account to Alice’s account. We will use two sessions for viewing the change of each operation.
-   In the first session, start a new transaction:

![](media/2d7d07473d0fc265d946c33b91377199.png)

-   Subtracting 1000USD from Bob’s account with id 1:

![](media/ad1903c87e5018269947795ceec5d7b5.png)

-   In the second session, check the account balance of both accounts:

![](media/3e63a2a3abcc526dee2bd2b601772be7.png)

**Output:**

![](media/ad2eb8984544e763c0d7b582fdc85fcd.png)

-   As you can see, the change is not visible in other sessions.
-   Next, add the same amount (1000USD ) to Alice’s account:

![](media/aa952cd906c3807f6053def8b6c5245a.png)

-   This change also is not visible to the second session until we commit it:

![](media/f6faad1463bc0ed900d34e14d0c0f477.png)

-   Now, you can view the change from any session:

![](media/70ef30d916be1080158280345b66015d.png)

**Output**

![](media/6981965f9b16d9909d253a670fc6f002.png)

-   Put it all together.

![](media/011fa9bb4addaa328a411b4361454c46.png)

## 2.3 Rolling back a Transaction

-   To roll back or undo the change of the current transaction,
-   you use any one of the following syntax for rollback statement:

![](media/5c5ca5871b5e807e1d6db6ebde756114.png)

Or

![](media/a91d19a0d5844336f5501ea7c84b8d26.png)

or in short:

![](media/729604b184d92f431f0acf60ca69fa25.png)

-   Suppose, you want to transfer 1500USD from Bob’s account to Alice’s account. However, you accidentally send the money to Jack’s account instead of Alice’s. And you want to roll back the whole transaction.
-   First, add Jack’s account to the accounts table:

![](media/56eb04f6d08e8e47d5464be848964dd1.png)

-   Next, subtract an amount from Bob’s account:

![](media/0a26c9398b278c7858017ccb4f82dfc8.png)

-   Then, adding the same amount to Alice’s account:

![](media/4ef9620dc22208cca74469f731b2e7a9.png)

-   However, Alice’s account has id 2. So this was a mistake.
-   To undo the change, you execute the ROLLBACK statement:

![](media/a456cbf89d0ed3f7841c6a3b01a13e51.png)

-   Finally, check the balances of all accounts:

![](media/395c5b6f86836b75b24e78e4be623896.png)

**Output**

![](media/3ff3678dd7f189acd3a6fe369a69adc1.png)

-   As shown clearly in the output, the account balances remain the same as they were before the transaction.
-   Put it all toegher.

![](media/a13b570873c97cf84ae86b027361b4ab.png)

## 2.4 Savepoint a Transaction

-   SAVEPOINT command is used to temporarily save a transaction so that you can rollback to that point whenever required.
-   Following is savepoint command's syntax,

![](media/3b971b48054281d695d80eb92851c0de.png)

-   SAVEPOINT establishes a new savepoint within the current transaction.
-   A savepoint is a special mark inside a transaction that allows all commands that are executed after it was established to be rolled back, restoring the transaction state to what it was at the time of the savepoint.

**Parameters**

**savepoint_name**

-   The name to give to the new savepoint. If savepoints with the same name already exist, they will be inaccessible until newer identically-named savepoints are released.

**Notes**

-   Use ROLLBACK TO to rollback to a savepoint. Use RELEASE SAVEPOINT to destroy a savepoint, keeping the effects of commands executed after it was established.
-   Savepoints can only be established when inside a transaction block. There can be multiple savepoints defined within a transaction.

## 2.5 Savepoint Examples

**1) To establish a savepoint and later undo the effects of all commands executed after it was established**

![](media/6e9902ee4599a1bd647f6d3beb431391.png)

-   The above transaction will insert the values 1 and 3, but not 2.

**2) To establish and later destroy a savepoint**

![](media/f2db538fe8fe9bf3e62e91dbc2072fe1.png)

-   The above transaction will insert both 3 and 4.

**3) To use a single savepoint name**

![](media/03f134f38a458b0328e257a9ca589d44.png)

-   The above transaction shows row 3 being rolled back first, then row 2.

## 3. References

1.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-transaction/
2.  https://www.postgresql.org/docs/current/sql-savepoint.html
