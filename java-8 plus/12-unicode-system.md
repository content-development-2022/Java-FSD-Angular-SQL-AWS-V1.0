# Unicode System

**Content**

1\. Unicode System

1.1 Why java uses Unicode System?

1.2 Problem

1.3 Solution

2\. References

## 1. Unicode System

-   Unicode is a universal international standard character encoding that is capable of representing most of the world's written languages.

## 1.1 Why java uses Unicode System?

-   Before Unicode, there were many language standards:
1.  **ASCII** (American Standard Code for Information Interchange) for the United States.
2.  **ISO 8859-1** for Western European Language.
3.  **KOI-8** for Russian.
4.  **GB18030 and BIG-5** for chinese, and so on.

## 1.2 Problem

**This caused two problems:**

-   A particular code value corresponds to different letters in the various language standards.
-   The encodings for languages with large character sets have variable length.
-   Some common characters are encoded as single bytes, other require two or more byte.

## 1.3 Solution

-   To solve these problems, a new language standard was developed i.e. Unicode System.
-   In unicode, character holds 2 byte, so java also uses 2 byte for characters.

**lowest value:**\\u0000

**highest value:**\\uFFFF

## 2. References

1.  https://www.javatpoint.com/unicode-system-in-java
