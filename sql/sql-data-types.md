## SQL Data Types

**Content**

**1. SQL Data Types**

1.1 Boolean

1.2 Character

1.2.1 CHAR(n)

1.2.2 VARCHAR(n)

1.2.3 TEXT

1.3 Numeric

1.3.1 Integer

1.3.2 Floating-point number

1.4 Temporal data types

1.5 Arrays

1.6 JSON

1.7 UUID

1.8 Special data types

**2. References**

## 1. SQL Data Types

SQL supports the following data types:

-   **Boolean**
-   **Character** types such as char, varchar, and text.
-   **Numeric** types such as integer and floating-point number.
-   **Temporal** types such as date, time, timestamp, and interval
-   **UUID** for storing Universally Unique Identifiers
-   **Array** for storing array strings, numbers, etc.
-   **JSON** stores JSON data
-   **hstore** stores key-value pair
-   **Special types** such as network address and geometric data.

## 1.1 Boolean

-   A Boolean data type can hold one of three possible values: true, false or null.
-   You use **boolean or bool** keyword to declare a column with the Boolean data type.
-   When you insert data into a Boolean column, PostgreSQL converts it to a Boolean value
1.  1, yes, y, t, true values are converted to true
2.  0, no, false, f values are converted to false.
-   When you select data from a Boolean column, PostgreSQL converts the values back e.g., t to true, f to false and space to null.

## 1.2 Character

-   PostgreSQL provides three character data types: **CHAR(n), VARCHAR(n), and TEXT**

## 1.2.1 CHAR(n)

-   CHAR(n) is the fixed-length character with space padded.
-   If you insert a string that is shorter than the length of the column, PostgreSQL pads spaces.
-   If you insert a string that is longer than the length of the column, PostgreSQL will issue an error.

## 1.2.2 VARCHAR(n)

-   VARCHAR(n) is the variable-length character string.
-   With VARCHAR(n), you can store up to n characters.
-   PostgreSQL does not pad spaces when the stored string is shorter than the length of the column.

## 1.2.3 TEXT

-   TEXT is the variable-length character string.
-   Theoretically, text data is a character string with unlimited length.

## 1.3 Numeric

PostgreSQL provides two distinct types of numbers:

-   integers
-   floating-point numbers

## 1.3.1 Integer

There are three kinds of integers in PostgreSQL:

-   **Small integer** ( SMALLINT) is 2-byte signed integer that has a range from -32,768 to 32,767.
-   **Integer** ( INT) is a 4-byte integer that has a range from -2,147,483,648 to 2,147,483,647.
-   **Serial** is the same as integer except that PostgreSQL will automatically generate and populate values into the SERIAL column. This is similar to AUTO_INCREMENT column in MySQL or AUTOINCREMENT column in SQLite.

## 1.3.2 Floating-point number

There three main types of floating-point numbers:

-   **float(n)** is a floating-point number whose precision, at least, n, up to a maximum of 8 bytes.
-   **real or float8** is a 4-byte floating-point number.
-   **numeric or numeric(p,s)** is a real number with p digits with s number after the decimal point. The numeric(p,s) is the exact number.

## 1.4 Temporal data types

-   The temporal data types allow you to store date and /or time data.
-   PostgreSQL has five main temporal data types:
1.  **DATE** stores the dates only.
2.  **TIME** stores the time of day values.
3.  **TIMESTAMP** stores both date and time values.
4.  **TIMESTAMPTZ** is a timezone-aware timestamp data type. It is the abbreviation for timestamp with the time zone.
5.  **INTERVAL** stores periods of time.

The TIMESTAMPTZ is the PostgreSQL’s extension to the SQL standard’s temporal data types.

## 1.5 Arrays

-   In PostgreSQL, you can store an array of strings, an array of integers, etc., in array columns.
-   The array comes in handy in some situations e.g., storing days of the week, months of the year.

## 1.6 JSON

-   PostgreSQL provides two JSON data types: JSON and JSONB for storing JSON data.
-   The JSON data type stores plain JSON data that requires reparsing for each processing, while JSONB data type stores JSON data in a binary format which is faster to process but slower to insert.
-   In addition, JSONB supports indexing, which can be an advantage.

## 1.7 UUID

-   The UUID data type allows you to store Universal Unique Identifiers defined by RFC 4122 .
-   The UUID values guarantee a better uniqueness than SERIAL and can be used to hide sensitive data exposed to the public such as values of id in URL.

## 1.8 Special data types

Besides the primitive data types, PostgreSQL also provides several special data types related to geometric and network.

-   box– a rectangular box.
-   line – a set of points.
-   point– a geometric pair of numbers.
-   lseg– a line segment.
-   polygon– a closed geometric.
-   inet– an IP4 address.
-   macaddr– a MAC address.

## 2. References

1.  https://www.postgresqltutorial.com/postgresql-tutorial/postgresql-data-types/
