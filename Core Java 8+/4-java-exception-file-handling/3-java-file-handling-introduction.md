**File Handling in Java**

In Java, with the help of File Class, we can work with files. This File Class is inside the java.io package. The File class can be used by creating an object of the class and then specifying the name of the file.

**Why File Handling is Required?**

-   File Handling is an integral part of any programming language as file handling enables us to store the output of any particular program in a file and allows us to perform certain operations on it.
-   In simple words, file handling means reading and writing data to a file.

// Importing File Class

import java.io.File;

class GFG {

public static void main(String[] args)

{

// File name specified

File obj = new File("myfile.txt");

System.out.println("File Created!");

}

}

**Output**

File Created!

In Java, the concept Stream is used in order to perform I/O operations on a file. So at first, let us get acquainted with a concept known as Stream in Java.

### Streams in Java

-   In Java, a sequence of data is known as a stream.
-   This concept is used to perform I/O operations on a file.
-   There are two types of streams :

#### **1. Input Stream:**

The Java InputStream class is the superclass of all input streams. The input stream is used to read data from numerous input devices like the keyboard, network, etc. InputStream is an abstract class, and because of this, it is not useful by itself. However, its subclasses are used to read data.

There are several subclasses of the InputStream class, which are as follows:

1.  AudioInputStream
2.  ByteArrayInputStream
3.  FileInputStream
4.  FilterInputStream
5.  StringBufferInputStream
6.  ObjectInputStream

#### Creating an InputStream

// Creating an InputStream

InputStream obj = new FileInputStream();

Here, an input stream is created using FileInputStream.

*Note: We can create an input stream from other subclasses as well as InputStream.*

#### Methods of InputStream

#### Methods of InputStream

| S No. | Method               | Description                                                                       |
|-------|----------------------|-----------------------------------------------------------------------------------|
| 1     | read()               | Reads one byte of data from the input stream.                                     |
| 2     | read(byte[] array)() | Reads byte from the stream and stores that byte in the specified array.           |
| 3     | mark()               | It marks the position in the input stream until the data has been read.           |
| 4     | available()          | Returns the number of bytes available in the input stream.                        |
| 5     | markSupported()      | It checks if the mark() method and the reset() method is supported in the stream. |
| 6     | reset()              | Returns the control to the point where the mark was set inside the stream.        |
| 7     | skips()              | Skips and removes a particular number of bytes from the input stream.             |
| 8     | close()              | Closes the input stream.                                                          |

#### **2. Output Stream:**

The output stream is used to write data to numerous output devices like the monitor, file, etc. OutputStream is an abstract superclass that represents an output stream. OutputStream is an abstract class and because of this, it is not useful by itself. However, its subclasses are used to write data.

There are several subclasses of the OutputStream class which are as follows:

1.  ByteArrayOutputStream
2.  FileOutputStream
3.  StringBufferOutputStream
4.  ObjectOutputStream
5.  DataOutputStream
6.  PrintStream

#### Creating an OutputStream

// Creating an OutputStream

OutputStream obj = new FileOutputStream();

Here, an output stream is created using FileOutputStream.

*Note: We can create an output stream from other subclasses as well as OutputStream.*

#### Methods of OutputStream

| S. No. | Method              | Description                                                                  |
|--------|---------------------|------------------------------------------------------------------------------|
| 1.     | write()             | Writes the specified byte to the output stream.                              |
| 2.     | write(byte[] array) | Writes the bytes which are inside a specific array to the output stream.     |
| 3.     | close()             | Closes the output stream.                                                    |
| 4.     | flush()             | Forces to write all the data present in an output stream to the destination. |

**Based on the data type, there are two types of streams :**

#### **1. Byte Stream:**

This stream is used to read or write byte data. The byte stream is again subdivided into two types which are as follows:

-   **Byte Input Stream:** Used to read byte data from different devices.
-   **Byte Output Stream:** Used to write byte data to different devices.

#### **2. Character Stream:**

This stream is used to read or write character data. Character stream is again subdivided into 2 types which are as follows:

-   **Character Input Stream:** Used to read character data from different devices.
-   **Character Output Stream:** Used to write character data to different devices.

Owing to the fact that you know what a stream is, let’s polish up File Handling in Java by further understanding the various methods that are useful for performing operations on the files like creating, reading, and writing files.

### Java File Class Methods

The following table depicts several File Class methods:

| Method Name           | Description                                     | Return Type |
|-----------------------|-------------------------------------------------|-------------|
| **canRead()**         | It tests whether the file is readable or not.   | Boolean     |
| **canWrite()**        | It tests whether the file is writable or not.   | Boolean     |
| **createNewFile()**   | It creates an empty file.                       | Boolean     |
| **delete()**          | It deletes a file.                              | Boolean     |
| **exists()**          | It tests whether the file exists or not.        | Boolean     |
| **length()**          | Returns the size of the file in bytes.          | Long        |
| **getName()**         | Returns the name of the file.                   | String      |
| **list()**            | Returns an array of the files in the directory. | String[]    |
| **mkdir()**           | Creates a new directory.                        | Boolean     |
| **getAbsolutePath()** | Returns the absolute pathname of the file.      | String      |

References:

https://www.geeksforgeeks.org/file-handling-in-java/
