# Stack Memory, Heap Memory and Garbage Collection Java

**Content**

1\. Introduction of Stack and Heap in Java

2\. Stack Memory

3\. Heap Memory

4\. Difference between Stack and Heap Memory

5\. Java Garbage Collection

5.1 Advantage of Garbage Collection

5.2 How can an object be unreferenced?

6\. References

## 1. Introduction of Stack and Heap in Java

-   In Java, memory management is a vital process.
-   It is managed by Java automatically.
-   The JVM divides the memory into two parts: stack memory and heap memory.
-   From the perspective of Java, both are important memory areas but both are used for different purposes.
-   The **major difference between Stack memory and heap memory** is that the stack is used to store the order of method execution and local variables while the heap memory stores the objects and it uses dynamic memory allocation and deallocation.

![](media/e600078a4d5092244eace8c9c602d343.png)

## 2. Stack Memory

-   The stack memory is a physical space (in RAM) allocated to each thread at run time.
-   It is created when a thread creates.
-   Memory management in the stack follows LIFO (Last-In-First-Out) order because it is accessible globally.
-   It stores the variables, references to objects, and partial results.
-   Memory allocated to stack lives until the function returns.
-   If there is no space for creating the new objects, it throws the **java.lang.StackOverFlowError.**
-   The scope of the elements is limited to their threads.

**Example of Stack Memory in Java**

![](media/f2d448af5428ec58622f7620ac193335.png)

![](media/801f4008541ac4455a363aaa5381115d.png)

**Explanation:**

1.  When the program is executed, the main method is executed first by the JVM. When the main method is called, a block is allocated for it in the call stack.
2.  The main method contains one primitive value x. This primitive value is stored in the memory block allocated for the main method.
3.  When the addOne method is called from the main method, a new block for addOne method is allocated in the stack memory.
4.  The variables specific to the method are created and stored in the allocated memory block. Upon the completion of the execution of the method, the value is returned to the calling method(here it is the main method), and the block is removed from the call stack.
5.  Similarly, when the addTwo method is called, a new block is allocated for it, and the variables are created and stored. When the method finishes execution, the value is returned to the calling method, and the block is cleared.
6.  Finally, the main method completes its execution, and the memory block corresponding to main method is cleared from the stack.

**What is StackOverflowError in Java?**

-   Stack memory is limited in size and cannot be enlarged or shrunk once created.
-   Therefore, if we use all of the stack memory, there will be no space left for upcoming method calls, and we will get the StackOverflowError.

**Example:**

![](media/31845a8e5a09a09f66b9ef05fbf1f739.png)

Error:

![](media/1309e7faa77ca2e6216ced85956fca12.png)

**Explanation:**

-   A new block on the stack is allocated for each call to the factorial method.
-   When the above program is executed, the factorial method will be called **indefinitely** because the base case is commented.
-   As the stack size is fixed, and the factorial method is called indefinitely and doesn't return any value, so the stack memory runs out, resulting in StackOverflowError.

![](media/6fed7e62ea07e02d5ada226409fa7dbc.png)

## 3. Heap Memory

-   It is created when the JVM starts up and used by the application as long as the application runs.
-   It stores objects and JRE classes.
-   Whenever we create objects it occupies space in the heap memory while the reference of that object creates in the stack.
-   It does not follow any order like the stack.
-   It dynamically handles the memory blocks.
-   It means, we need not to handle the memory manually.
-   For managing the memory automatically, Java provides the garbage collector that deletes the objects which are no longer being used.
-   Memory allocated to heap lives until any one event, either program terminated or memory free does not occur.
-   The elements are globally accessible in the application.
-   It is a common memory space shared with all the threads.
-   If the heap space is full, it throws the java.lang.OutOfMemoryError.

**Example of Heap Memory in Java**

![](media/06bd64bb357abd8bca9a21e5f3355fdb.png)

**Explanation:**

-   In the above example, the variable x is allocated in the stack, whereas the object list is allocated memory in the heap.
-   Only the reference to the list object is stored in the stack memory alongside x.

![](media/78b90617b11edabccb676c44fe881d2a.png)

**Why OutOfMemoryError is thrown in Java?**

-   **OutOfMemoryError** is thrown when there is no more space left in the heap to create and store a new object.
-   This happens when the Garbage Collector could not freeup any space to store new objects.

![](media/358d9716f1d81f930d72f82e81c9e402.png)

**Error**

![](media/3ecfa886f818e352301248596a60ed5a.png)

**Explanation:**

-   Consider the above program where we are repeatedly generating arrays of bigger sizes and storing values in them.
-   Once the space ran out in the heap, it threw OutOfMemoryError.

## 4. Difference between Stack and Heap Memory

The following table summarizes all the major differences between stack memory and heap space.

![](media/e782e0a6968fcd763693c54aeb4298df.png)

## 5. Java Garbage Collection

-   When JVM starts up, it creates a **heap area** which is known as **runtime data area.**
-   This area is used to store all the objects (instances of class).
-   Since this area is limited, it is required to manage this area efficiently by removing the objects that are no longer in use.
-   The process of removing unused objects from heap memory is known as **Garbage collection** and this is a part of memory management in Java.
-   Languages like C/C++ **don’t** support automatic garbage collection, however in java, the garbage collection is automatic.
-   In java, garbage means unreferenced objects.

## 5.1 Advantage of Garbage Collection

-   It makes java **memory efficient** because garbage collector removes the unreferenced objects from heap memory.
-   It is **automatically done** by the garbage collector(a part of JVM) so we don't need to make extra efforts.

## 5.2 How can an object be unreferenced?

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

## 6. References

1.  https://www.javatpoint.com/stack-vs-heap-java
2.  https://www.scaler.com/topics/java/heap-memory-and-stack-memory-in-java/
3.  https://www.javatpoint.com/Garbage-Collection
4.  https://beginnersbook.com/2013/04/java-garbage-collection/
