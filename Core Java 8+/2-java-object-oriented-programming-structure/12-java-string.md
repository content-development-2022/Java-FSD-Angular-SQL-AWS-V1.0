# Java String

**Content**

1\. Java String

2\. String Methods

2.1 String toUpperCase() and toLowerCase()

2.2 String Length

2.3 Finding a Character in a String

2.4 String Concatenation

3\. Adding Numbers and Strings

4\. Strings - Special Characters

5\. References

## 1. Java Strings

-   Strings are used for storing text.
-   A String variable contains a collection of characters surrounded by double quotes.

**Example**

String greeting = "Hello";

## 2. String Methods

-   A String in Java is actually an object, which contain methods that can perform certain operations on strings.
-   There are many string methods available.

## 2.1 String toUpperCase() and toLowerCase()

**Example**

![](media/83d39c597c4ad9735c6ed0211ff10ac9.png)

## String Length

-   The length of a string can be found with the length() method.

**Example**

![](media/b074a4fc938ca9b30bec6cd917b0dba0.png)

**Output**

![](media/6ed6dc1a26cd122fd2375300a50149d5.png)

## 2.3 Finding a Character in a String

-   The indexOf() method returns the **index** (the position) of the first occurrence of a specified text in a string (including whitespace):

**Example**

![](media/29944a1048b74d1ac9e00e4a73d544fd.png)

![](media/420a9ab9d61613a13989d00280e801f3.png)

## 2.4 String Concatenation

-   The + operator can be used between strings to combine them. This is called **concatenation**.

**Example**

![](media/3fe4773cbe1b37ae8d158c25d8a5cfd6.png)

![](media/6c9f4314f677a31ad58e33cd6bec08d5.png)

-   You can also use the concat() method to concatenate two strings.

**Example**

![](media/a26052dd0c2209030fabe4296441c011.png)

## 3. Adding Numbers and Strings

![](media/5b16f0c0549330c98553b24eec240722.png)

**1) If you add two numbers, the result will be a number:**

**Example**

![](media/d8bc3222bf35773cb8396c556f2db980.png)

**2) If you add two strings, the result will be a string concatenation.**

**Example:**

![](media/5a231e7f6b15ca978e4b37406f4aba92.png)

**3) If you add a number and a string, the result will be a string concatenation.**

**Example:**

![](media/601b13f8e5dab928d549d49e31afaa1d.png)

## 4. Strings - Special Characters

-   strings must be written within quotes, Java will misunderstand this string, and generate an error.

**Example:**

![](media/f1499855240a405d3b2ec4b45bb52ad1.png)

![](media/9ee6958f5b63a1255a8f5632ec051254.png)

-   The solution to avoid this problem, is to use the **backslash escape character**.
-   The backslash (\\) escape character turns special characters into string characters.

![](media/0e905d10c0e5f24f515a0e938992286e.png)

**1) The sequence \\" inserts a double quote in a string.**

**Example:**

![](media/84521ea142092ddd7bd776bbcb55949c.png)

**2) The sequence \\' inserts a single quote in a string.**

**Example:**

![](media/fd38b9a1bd0b3c2363d9374dd55613f2.png)

**3) The sequence \\\\ inserts a single backslash in a string.**

**Example:**

![](media/a047b64dc3386a4304d5c31161049ab6.png)

-   Other common escape sequences that are valid in Java are:

![](media/ca3a5e96bbd8dae7d8209cc0b5a82c28.png)

## 5. References

1.  https://www.w3schools.com/java/java_strings.asp
2.  https://www.w3schools.com/java/java_strings_concat.asp
3.  https://www.w3schools.com/java/java_strings_numbers.asp
4.  https://www.w3schools.com/java/java_strings_specchars.asp
