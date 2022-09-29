# How to set path in Java

**Content**

1\. How to set path in Java

1.1 How to set the Temporary Path of JDK in Windows

1.2 How to set the Permanent Path of JDK in Windows

2\. References

## 1. How to set path in Java

-   The path is required to be set for using tools such as javac, java, etc.
-   If you are saving the Java source file inside the JDK/bin directory, the path is not required to be set because all the tools will be available in the current directory.
-   However, if you have your Java file outside the JDK/bin folder, it is necessary to set the path of JDK.
-   There are two ways to set the path in Java:
1.  Temporary
2.  Permanent

## 1.1 How to set the Temporary Path of JDK in Windows

To set the temporary path of JDK, you need to follow the following steps:

-   Open the command prompt
-   Copy the path of the JDK/bin directory
-   Write in command prompt: **set path=copied_path**

**Example**

![](media/4566045be86a3d586ac3b051bf658005.png)

-   Let's see it in the figure given below:

![](media/0ac608d0d404a8d9ec92921dcdaee79f.png)

## 1.2 How to set the Permanent Path of JDK in Windows

For setting the permanent path of JDK, you need to follow these steps:

-   Go to **MyComputer -\> properties -\> advances system settings -\> advanced tab -\> environment variables -\> new tab of user variable -\>** write path in **variable name -\>** write path of bin folder in **variable value -\> ok -\> ok -\> ok**

**Example**

**Step1:** Go to MyComputer and right click on **mycomputer. Click on properties.**

![](media/7ca500bf54020bac42dfa0de0d734254.png)

**Step2:** Click on the **advanced system settings.**

![](media/d711f239a6da48107fb3d2e5fd3def89.png)

**Step3:** Click on the **advanced tab.**

![](media/6fcd6380843b774be2c40d7b4329d09f.png)

**Step4:** Click on **environment variables.**

![](media/370f5b52056724b6d6aa524e4fc471b4.png)

**Step5:** Click on the **new** button of **user variables.**

![](media/2c8f4c62c51de314006f3c31ee3ac033.png)

**Step6:** Write the **path** in the **variable name.**

![](media/e8cc708a1bd8a7241cd7fa8cd85134af.png)

**Step7:** Copy the path of **bin folder.**

![](media/c2a809af9336398ae58d87ab98a81329.png)

**Step8:**  Paste **path of bin folder** in the **variable value.**

![](media/3cea28a7239b37e0015082203a180afe.png)

**Step9:** Click on **ok** button.

![](media/c726f8a6db992142565d226b69ba6203.png)

**Step10:** Click on **ok** button.

![](media/2273b07a2f54c1b5cc155c8de368df97.png)

**Step11:** Click on **ok** button.

![](media/0a08c417e7da9c2245a3e6fdbd82f3cb.png)

-   Now your permanent path is set.
-   You can now execute any program of java from any drive.

## 2. References

1.  https://www.javatpoint.com/how-to-set-path-in-java
