# Java Garbage Collection

**Content**

1\. Java Garbage Collection

1.1 Advantage of Garbage Collection

1.2 How can an object be unreferenced?

2\. References

## 1. Java Garbage Collection

-   When JVM starts up, it creates a **heap area** which is known as **runtime data area.**
-   This area is used to store all the objects (instances of class).
-   Since this area is limited, it is required to manage this area efficiently by removing the objects that are no longer in use.
-   The process of removing unused objects from heap memory is known as **Garbage collection** and this is a part of memory management in Java.
-   Languages like C/C++ **don’t** support automatic garbage collection, however in java, the garbage collection is automatic.
-   In java, garbage means unreferenced objects.

## 1.1 Advantage of Garbage Collection

-   It makes java **memory efficient** because garbage collector removes the unreferenced objects from heap memory.
-   It is **automatically done** by the garbage collector(a part of JVM) so we don't need to make extra efforts.

## 1.2 How can an object be unreferenced?

![](media/5428908a18ce14fc0dc77fa78330cf75.png)

**1) By nulling a reference:**

![](media/1bfb940d7b6fc8a7821c6640e4e48d59.png)

**2) By assigning a reference to another:**

![](media/4b7e7f0f37292f4c4b107100b341752e.png)

**3) By anonymous object:**

![](media/43d99e4039f3aa5030b5fe09d450631a.png)

## finalize() method

-   The finalize() method is invoked each time before the object is garbage collected.
-   This method can be used to perform cleanup processing.
-   This method is defined in Object class as:

![](media/c8d790cbd23fcfdb9c5854b2a92dec8e.png)

![](media/89abb1ddd19c7dcb77eca48caa4453e2.png)

## gc() method

-   The gc() method is used to invoke the garbage collector to perform cleanup processing.
-   The gc() is found in System and Runtime classes.

![](media/6b9e820e9a2b831ecb0dfa695eeaa5cf.png)

![](media/9ddc3a97c17512fb9c4a188cefd097ab.png)

**Simple Example of garbage collection in java**

![](media/65bd2788eee80d6fdfca7f8aca7a3b91.png)

![](media/ef16e816da294dbd6aebaea7ce242f95.png)

![](media/71fbe5893adbb80b964d95b39eac1e7b.png)

## 2. References

1.  https://www.javatpoint.com/Garbage-Collection
2.  https://beginnersbook.com/2013/04/java-garbage-collection/
