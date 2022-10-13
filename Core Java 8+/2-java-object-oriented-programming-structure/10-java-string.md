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

**![](media/66beaa09be650ec9e396c69b8a778e5f.png)**

**Output**:

![](media/f618f5d61914491780c6cba356929c84.png)

## 2.2 String Length

-   The length of a string can be found with the length() method.

**Example**

![](media/4df331acc4c5e20b5f52d0f6525fd726.png)

**Output**

**![](media/6f1f03b187c40f9f1ff4ac30e8aa5bb9.png)**

## 2.3 Finding a Character in a String

-   The indexOf() method returns the **index** (the position) of the first occurrence of a specified text in a string (including whitespace):

**Example**

![](media/d946da550de7747952ead1d447c33a27.png)

**Output:**

**![](media/1acf5bc0a8afdf53c12ff558955cb37f.png)**

## 2.4 String Concatenation

-   The + operator can be used between strings to combine them. This is called **concatenation**.

**Example**

![](media/8e1db84b9453e0df0e721cecd101af49.png)

**Output:**

![](media/fc7122eb1cbc86ad36d6321d6f3ab93a.png)

-   You can also use the concat() method to concatenate two strings.

**Example**

![](media/de7e21c936cbcc6f12b8beb0eca7c750.png)

## 3. Adding Numbers and Strings

![](media/8129419aaac5ac83a7568b6fde4fdd97.png)

**1) If you add two numbers, the result will be a number:**

**Example**

![](media/b024993be537f980d1fa48a38641e68b.png)

**2) If you add two strings, the result will be a string concatenation.**

**Example:**

![](media/653183f76f912569a1c1054c98327c1e.png)

**3) If you add a number and a string, the result will be a string concatenation.**

**Example:**

![](media/c23b00d9d561ebff568d9c8e8f3d6430.png)

## 4. Strings - Special Characters

-   Strings must be written within quotes, Java will misunderstand this string, and generate an error.

**Example:**

![](media/a7d440042a3ff7a39609e7fad4e5d3e4.png)

-   The solution to avoid this problem, is to use the **backslash escape character**.
-   The backslash (\\) escape character turns special characters into string characters.

![](media/6c94ef5140572f88b8711f3813bf5b96.png)

**1) The sequence \\" inserts a double quote in a string.**

**Example:**

![](media/344b541aaa8a66fda5cc8d4735e30c30.png)

**2) The sequence \\' inserts a single quote in a string.**

**Example:**

![](media/d181801ef4e33bfd137e7e59c4c3ea45.png)

**3) The sequence \\\\ inserts a single backslash in a string.**

**Example:**

![](media/8c99366877205ce0fa2f7b2e0eae3724.png)Other common escape sequences that are valid in Java are:

![](media/00afb09659129c2aa2d3b6ddcbc18ad3.png)

## 5. References

1.  https://www.w3schools.com/java/java_strings.asp
2.  https://www.w3schools.com/java/java_strings_concat.asp
3.  https://www.w3schools.com/java/java_strings_numbers.asp
4.  https://www.w3schools.com/java/java_strings_specchars.asp
