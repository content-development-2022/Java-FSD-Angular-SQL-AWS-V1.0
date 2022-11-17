# JDBC – Introduction

**Content**

[1. What is JDBC?](#1-what-is-jdbc)

[2. JDBC Architecture](#2-jdbc-architecture)

[3. The JDBC 4.0 Packages](#3-the-jdbc-40-packages)

[4. References](#4-references)

# 1. What is JDBC?

-   JDBC stands for **J**ava **D**ata**b**ase **C**onnectivity, which is a standard Java API for database-independent connectivity between the Java programming language and a wide range of databases.
-   The JDBC library includes APIs for each of the tasks mentioned below that are commonly associated with database usage.
1.  Making a connection to a database.
2.  Creating SQL or MySQL statements.
3.  Executing SQL or MySQL queries in the database.
4.  Viewing & Modifying the resulting records.

## 1.1 Applications of JDBC

-   Fundamentally, JDBC is a specification that provides a complete set of interfaces that allows for portable access to an underlying database.
-   Java can be used to write different types of executables, such as −
1.  Java Applications
2.  Java Applets
3.  Java Servlets
4.  Java ServerPages (JSPs)
5.  Enterprise JavaBeans (EJBs).
-   All of these different executables are able to use a JDBC driver to access a database, and take advantage of the stored data.
-   JDBC provides the same capabilities as ODBC, allowing Java programs to contain database-independent code.

## 1.2 Pre-Requisite

-   Before moving further, you need to have a good understanding of the following two subjects −
-   Core JAVA Programming
-   SQL or MySQL Database

# 2. JDBC Architecture

-   The JDBC API supports both two-tier and three-tier processing models for database access but in general, JDBC Architecture consists of two layers −
1.  **JDBC API** − This provides the application-to-JDBC Manager connection.
2.  **JDBC Driver API** − This supports the JDBC Manager-to-Driver Connection.
-   The JDBC API uses a driver manager and database-specific drivers to provide transparent connectivity to heterogeneous databases.
-   The JDBC driver manager ensures that the correct driver is used to access each data source.
-   The driver manager is capable of supporting multiple concurrent drivers connected to multiple heterogeneous databases.
-   Following is the architectural diagram, which shows the location of the driver manager with respect to the JDBC drivers and the Java application −

![JDBC Architecture](media/architecture-jdbc.png)

## 2.1 Common JDBC Components

The JDBC API provides the following interfaces and classes −

**DriverManager**:

-   This class manages a list of database drivers.
-   Matches connection requests from the java application with the proper database driver using communication sub protocol.
-   The first driver that recognizes a certain subprotocol under JDBC will be used to establish a database Connection.

**Driver**:

-   This interface handles the communications with the database server.
-   You will interact directly with Driver objects very rarely.
-   Instead, you use DriverManager objects, which manages objects of this type.
-   It also abstracts the details associated with working with Driver objects.

**Connection**:

-   This interface with all methods for contacting a database.
-   The connection object represents communication context, i.e., all communication with database is through connection object only.

**Statement**:

-   You use objects created from this interface to submit the SQL statements to the database.
-   Some derived interfaces accept parameters in addition to executing stored procedures.

**ResultSet** :

-   These objects hold data retrieved from a database after you execute an SQL query using Statement objects.
-   It acts as an iterator to allow you to move through its data.

**SQLException**:

-   This class handles any errors that occur in a database application.

## 3. The JDBC 4.0 Packages

-   The java.sql and javax.sql are the primary packages for JDBC 4.0.
-   This is the latest JDBC version at the time of writing this tutorial.
-   It offers the main classes for interacting with your data sources.

**The new features in these packages include changes in the following areas −**

-   Automatic database driver loading.
-   Exception handling improvements.
-   Enhanced BLOB/CLOB functionality.
-   Connection and statement interface enhancements.
-   National character set support.
-   SQL ROWID access.
-   SQL 2003 XML data type support.
-   Annotations.

# 4. References

1.  https://www.tutorialspoint.com/jdbc/jdbc-introduction.htm
