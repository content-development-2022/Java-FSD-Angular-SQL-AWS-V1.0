# Aggregate and Scalar Functions

1.  **Aggregate functions:**  
    These functions are used to do operations from the values of the column and a single value is returned.
    1.  AVG()
    2.  COUNT()
    3.  FIRST()
    4.  LAST()
    5.  MAX()
    6.  MIN()
    7.  SUM()
2.  **Scalar functions:**  
    These functions are based on user input, these too returns single value.
    1.  UCASE()
    2.  LCASE()
    3.  MID()
    4.  LEN()
    5.  ROUND()
    6.  NOW()
    7.  FORMAT()

![](media/e6893b5c59875713c6e7e989cdadca5e.png)

**Aggregate Functions**

**AVG()**: It returns the average value after calculating from values in a numeric column.

**Syntax:**

SELECT AVG(column_name) FROM table_name;

**Queries:**

-   Computing average marks of students.

SELECT AVG(MARKS) AS AvgMarks FROM Students;

Output:

| **AvgMarks** |
|--------------|
| 80           |

-   Computing average age of students.

SELECT AVG(AGE) AS AvgAge FROM Students;

Output:

| **AvgAge** |
|------------|
| 19.4       |

**COUNT():** It is used to count the number of rows returned in a SELECT statement. It can’t be used in MS ACCESS.

**Syntax:**

SELECT COUNT(column_name) FROM table_name;

Queries:

-   Computing total number of students.

SELECT COUNT(\*) AS NumStudents FROM Students;

Output:

| **NumStudents** |
|-----------------|
| 5               |

-   Computing number of students with unique/distinct age.

SELECT COUNT(DISTINCT AGE) AS NumStudents FROM Students;

Output:

| **NumStudents** |
|-----------------|
| 4               |

**FIRST():** The FIRST() function returns the first value of the selected column.

**Syntax:**

SELECT FIRST(column_name) FROM table_name;

Queries:

-   Fetching marks of first student from the Students table.

SELECT FIRST(MARKS) AS MarksFirst FROM Students;

Output:

| **MarksFirst** |
|----------------|
| 90             |

-   Fetching age of first student from the Students table.

SELECT FIRST(AGE) AS AgeFirst FROM Students;

Output:

| **AgeFirst** |
|--------------|
| 19           |

**LAST():** The LAST() function returns the last value of the selected column. It can be used only in MS ACCESS.

**Syntax:**

SELECT LAST(column_name) FROM table_name;

**Queries:**

-   Fetching marks of last student from the Students table.

SELECT LAST(MARKS) AS MarksLast FROM Students;

Output:

| **MarksLast** |
|---------------|
| 85            |

-   Fetching age of last student from the Students table.

SELECT LAST(AGE) AS AgeLast FROM Students;

Output:

| **AgeLast** |
|-------------|
| 18          |

**MAX():** The MAX() function returns the maximum value of the selected column.

**Syntax:**

SELECT MAX(column_name) FROM table_name;

**Queries**:

-   Fetching maximum marks among students from the Students table.

SELECT MAX(MARKS) AS MaxMarks FROM Students;

Output:

| **MaxMarks** |
|--------------|
| 95           |

-   Fetching max age among students from the Students table.

SELECT MAX(AGE) AS MaxAge FROM Students;

Output:

| **MaxAge** |
|------------|
| 21         |

**MIN():** The MIN() function returns the minimum value of the selected column.

**Syntax:**

SELECT MIN(column_name) FROM table_name;

**Queries:**

-   Fetching minimum marks among students from the Students table.

SELECT MIN(MARKS) AS MinMarks FROM Students;

Output:

| **MinMarks** |
|--------------|
| 50           |

-   Fetching minimum age among students from the Students table.

SELECT MIN(AGE) AS MinAge FROM Students;

Output:

| **MinAge** |
|------------|
| 18         |

**SUM():** The SUM() function returns the sum of all the values of the selected column.

**Syntax:**

SELECT SUM(column_name) FROM table_name;

**Queries:**

-   Fetching summation of total marks among students from the Students table.

SELECT SUM(MARKS) AS TotalMarks FROM Students;

Output:

| **TotalMarks** |
|----------------|
| 400            |

-   Fetching summation of total age among students from the Students table.

SELECT SUM(AGE) AS TotalAge FROM Students;

Output:

| **TotalAge** |
|--------------|
| 97           |

**Scalar Functions**

**UCASE()**: It converts the value of a field to uppercase.

**Syntax:**

SELECT UCASE(column_name) FROM table_name;

**Queries:**

-   Converting names of students from the table Students to uppercase.

SELECT UCASE(NAME) FROM Students;

Output:

| **NAME** |
|----------|
| HARSH    |
| SURESH   |
| PRATIK   |
| DHANRAJ  |
| RAM      |

**LCASE()**: It converts the value of a field to lowercase.

**Syntax:**

SELECT LCASE(column_name) FROM table_name;

**Queries:**

-   Converting names of students from the table Students to lowercase.

SELECT LCASE(NAME) FROM Students;

Output:

| **NAME** |
|----------|
| harsh    |
| suresh   |
| pratik   |
| dhanraj  |
| ram      |

**MID():** The MID() function extracts texts from the text field.

**Syntax:**

SELECT MID(column_name,start,length) AS some_name FROM table_name;

specifying length is optional here, and start signifies start position ( starting from 1 )

**Queries:**

-   Fetching first four characters of names of students from the Students table.

SELECT MID(NAME,1,4) FROM Students;

Output:

| **NAME** |
|----------|
| HARS     |
| SURE     |
| PRAT     |
| DHAN     |
| RAM      |

**LEN():** The LEN() function returns the length of the value in a text field.

**Syntax:**

SELECT LENGTH(column_name) FROM table_name;

**Queries:**

-   Fetching length of names of students from Students table.

SELECT LENGTH(NAME) FROM Students;

Output:

| **NAME** |
|----------|
| 5        |
| 6        |
| 6        |
| 7        |
| 3        |

**ROUND():** The ROUND() function is used to round a numeric field to the number of decimals specified.NOTE: Many database systems have adopted the IEEE 754 standard for arithmetic operations, which says that when any numeric .5 is rounded it results to the nearest even integer i.e, 5.5 and 6.5 both gets rounded off to 6.

**Syntax:**

SELECT ROUND(column_name,decimals) FROM table_name;

decimals- number of decimals to be fetched.

**Queries:**

-   Fetching maximum marks among students from the Students table.

SELECT ROUND(MARKS,0) FROM table_name;

Output:

| **MARKS** |
|-----------|
| 90        |
| 50        |
| 80        |
| 95        |
| 85        |

**NOW():** The NOW() function returns the current system date and time.

Syntax:

SELECT NOW() FROM table_name;

**Queries:**

-   Fetching current system time.

SELECT NAME, NOW() AS DateTime FROM Students;

Output:

| **NAME** | **DateTime**         |
|----------|----------------------|
| HARSH    | 1/13/2017 1:30:11 PM |
| SURESH   | 1/13/2017 1:30:11 PM |
| PRATIK   | 1/13/2017 1:30:11 PM |
| DHANRAJ  | 1/13/2017 1:30:11 PM |
| RAM      | 1/13/2017 1:30:11 PM |

**FORMAT():** The FORMAT() function is used to format how a field is to be displayed.

**Syntax:**

SELECT FORMAT(column_name,format) FROM table_name;

**Queries:**

-   Formatting current date as ‘YYYY-MM-DD’.

SELECT NAME, FORMAT(Now(),'YYYY-MM-DD') AS Date FROM Students;

Output:

| **NAME** | **Date**   |
|----------|------------|
| HARSH    | 2017-01-13 |
| SURESH   | 2017-01-13 |
| PRATIK   | 2017-01-13 |
| DHANRAJ  | 2017-01-13 |
| RAM      | 2017-01-13 |

References

https://www.geeksforgeeks.org/sql-functions-aggregate-scalar-functions/
