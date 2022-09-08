# PostgreSQL

**Content**

**1. What is PostgreSQL**

1.1 Why use PostgreSQL?

**2. PostgreSQL on Windows**

2.1 Download PostgreSQL Installer for Windows

2.2 Install PostgreSQL on Window

2.3 Connect to a PostgreSQL Database Server

2.3.1 Connect to PostgreSQL database server using psql

2.3.2 Connect to PostgreSQL database server using pgAdmin

**3. References**

# 1. What is PostgreSQL

-   PostgreSQL is a powerful, open source object-relational database system that uses and extends the SQL language combined with many features that safely store and scale the most complicated data workloads.
-   PostgreSQL has earned a strong reputation for its proven architecture, reliability, data integrity, robust feature set, extensibility, and the dedication of the open source community behind the software to consistently deliver performant and innovative solutions.
-   PostgreSQL supports both SQL (relational) and JSON (non-relational) querying.

## 1.1 Why use PostgreSQL?

-   PostgreSQL comes with **many features** aimed to help developers build applications, administrators to protect data integrity and build fault-tolerant environments, and help you manage your data no matter how big or small the dataset.
-   In addition to being **free and open source**, PostgreSQL is highly extensible. For example, you can define your own data types, build out custom functions, even write code from **different programming languages** without recompiling your database!
-   Many of the features required by the SQL standard are supported, though sometimes with slightly differing syntax or function.

# 2. PostgreSQL on Windows

-   PostgreSQL was developed for UNIX-like platforms, however, it was designed to be portable. It means that PostgreSQL can also run on other platforms such as macOS, Solaris, and Windows.
-   Since version 8.0, PostgreSQL offers an installer for Windows systems that makes the installation process easier and faster. For development purposes, we will install PostgreSQL version 12 on Windows 10.

There are three steps to complete the PostgreSQL installation:

1.  Download PostgreSQL installer for Windows
2.  Install PostgreSQL
3.  Connect to a PostgreSQL Database Server

## 2.1 Download PostgreSQL Installer for Windows

-   First, you need to go to the download page of PostgreSQL installers on the EnterpriseDB.
-   Second, click the download link as shown below:

![](media/0ec4be9c5a7ebcf3e706f93efc195b91.png)

-   It will take a few minutes to complete the download.

## 2.2 Install PostgreSQL on Window

-   To install PostgreSQL on Windows, you need to have administrator privileges.

**Step 1.** Double click on the installer file, an installation wizard will appear and guide you through multiple steps where you can choose different options that you would like to have in PostgreSQL.

**Step 2.** Click the Next button.

![](media/807e20216e2924a32d8da9a5dce3979e.png)

**Step 3.** Specify installation folder, choose your own or keep the default folder suggested by PostgreSQL installer and click the Next button.

![](media/5dc710098b246c04965034f1c55c4782.png)

**Step 4.** Select software components to install:

-   The **PostgreSQL Server** to install the PostgreSQL database server.
-   **pgAdmin 4** to install the PostgreSQL database GUI management tool.
-   **Command Line Tools** to install command-line tools such as psql, pg_restore, etc. These tools allow you to interact with the PostgreSQL database server using the command-line interface.
-   Stack Builder provides a GUI that allows you to download and install drivers that work with PostgreSQL. You don’t need to install Stack Builder so feel free to uncheck it and click the Next button to select the data directory:

![](media/e257a1be377fcdddd0f85b887566fd09.png)

**Step 5.** Select the database directory to store the data or accept the default folder. And click the Next button to go to the next step:

![](media/c91bec1e8f1029149f721f7377070a57.png)

**Step 6.** Enter the password for the database superuser (postgres)

-   PostgreSQL runs as a service in the background under a service account named postgres. If you already created a service account with the name postgres, you need to provide the password of that account in the following window.
-   After entering the password, you need to retype it to confirm and click the Next button:

![](media/6d327d2df257ba5d75cb60e0e92cf719.png)

**Step 7.** Enter a port number on which the PostgreSQL database server will listen.

-   The default port of PostgreSQL is 5432. You need to make sure that no other applications are using this port.

![](media/4cd8b1eb1735125884072879b8115b45.png)

**Step 8.** Choose the default locale used by the PostgreSQL database. If you leave it as default locale, PostgreSQL will use the operating system locale. After that click the Next button.

![](media/280385b38d5e27857ab38d43ece0eb7b.png)

**Step 9.** The setup wizard will show the summary information of PostgreSQL. You need to review it and click the Next button if everything is correct. Otherwise, you need to click the Back button to change the configuration accordingly.

![](media/742cf547e1f4a0d9bd0fe7ed346e6cf0.png)

-   Now, you’re ready to install PostgreSQL on your computer. Click the **Next** button to begin installing PostgreSQL.

![](media/c561deafd6910ba7685663c30f0c1492.png)

-   The installation may take a few minutes to complete.

![](media/5cd0d983a2e1fb1c658d00c11987aabf.png)

**Step 10.** Click the **Finish** button to complete the PostgreSQL installation.

![](media/1aedc2415720cc81041de7d91e06447b.png)

# 2.3 Connect to a PostgreSQL Database Server

-   When you installed the PostgreSQL database server, the PostgreSQL installer also installed some useful tools for working with the PostgreSQL database server.
-   You will learn how to connect to the PostgreSQL database server via the following tools:
1.  **psql** – a terminal-based front-end to PostgreSQL database server.
2.  **pgAdmin** – a web-based front-end to PostgreSQL database server.

# 2.3.1 Connect to PostgreSQL database server using psql

-   psql is an interactive terminal program provided by PostgreSQL.
-   It allows you to interact with the PostgreSQL database server such as executing SQL statements and managing database objects.

**The following steps show you how to connect to the PostgreSQL database server via the psql program:**

**Step 1:** Launch the **psql** program and connect to the PostgreSQL Database Server using the **postgres** user:

![](media/21315b5272b1a038700e5f437926a0e5.png)

**Step 2:** Enter all the information such as Server, Database, Port, Username, and Password. If you press Enter, the program will use the default value specified in the square bracket [] and move the cursor to the new line. For example, localhost is the default database server. In the step for entering the password for user postgres, you need to enter the password the user postgres that you choose during the PostgreSQL installation.

![](media/458547e81475eb9ae6ef37271b8a5829.png)

**Step 3:** Interact with the PostgreSQL Database Server by issuing an SQL statement. The following statement returns the current version of PostgreSQL:

![](media/ff90760ad7ee4fe5b6cf0c3fca6a67e0.png)

![](media/99aa38f74f313248507c037b3ce815aa.png)

-   Please do not forget to end the statement with a semicolon (;). After pressing **Enter**, psql will return the current PostgreSQL version on your system.

## 2.3.2 Connect to PostgreSQL database server using pgAdmin

-   The second way to connect to a database is by using a pgAdmin application.
-   The pgAdmin application allows you to interact with the PostgreSQL database server via an intuitive user interface.

**The following illustrates how to connect to a database using pgAdmin GUI application:**

**Step 1:** Launch the pgAdmin application.

![](media/9b03eeb499d692f8dc7139253cb27b64.png)

-   The pgAdmin application will launch on the web browser as shown in the following picture:

![](media/fbe60fb504fcb43e6c4f54820917db7d.png)

**Step 2:** Right-click the Servers node and select **Create \> Server…** menu to create a server

![](media/03582ee7fb24fa55654755ee44a35606.png)

**Step 3:** Enter the server name e.g., **PostgreSQL** and click the **Connection** tab:

![](media/31f47d88564c22d64ef374889ca78473.png)

**Step 4:** Enter the host and password for the **postgres** user and click the **Save** button:

![](media/a51cb554334d9a06cb765bcb06b1c013.png)

**Step 5:** Click on the **Servers node** to expand the server. By default, PostgreSQL has a database named **postgres** as shown below:

![](media/0adef6423b92a01f303589a18a02c1c2.png)

**Step 6:** Open the query tool by choosing the menu item **Tool \> Query Tool** or click the **lightning icon.**

![](media/a419c145d2d2937c6bfb8993d5b4f586.png)

**Step 7:** Enter the query in the **Query Editor**, click the **Execute** button, you will see the result of the query displaying in the **Data Output** tab:

![](media/72048be81622db54e928020681d369ac.png)

## 3. References

1.  https://www.postgresqltutorial.com/postgresql-getting-started/what-is-postgresql/
2.  https://www.postgresqltutorial.com/postgresql-getting-started/install-postgresql/
3.  https://www.postgresqltutorial.com/postgresql-getting-started/connect-to-postgresql-database/
