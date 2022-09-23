# Java Flow Control Statements

**Content**

## 1. Java Flow Control Statements

-   Java compiler executes the code from top to bottom.
-   The statements in the code are executed according to the order in which they appear.
-   However, Java provides statements that can be used to control the flow of Java code. Such statements are called **control flow statements**.
-   It is one of the fundamental features of Java, which provides a smooth flow of program.
-   Java provides **three** types of control flow statements.

![](media/b8949b20450200bc19f85ede251d3154.png)

## 1.1 Decision-Making Statements

-   As the name suggests, decision-making statements decide which statement to execute and when.
-   Decision-making statements evaluate the Boolean expression and control the program flow depending upon the result of the condition provided.
-   There are **two types** of **decision-making statements** in Java, i.e., **If** statement and **switch** statement.

## 1.1.1 If Statement

-   In Java, the "if" statement is used to evaluate a condition.
-   The control of the program is diverted depending upon the specific condition.
-   The condition of the If statement gives a Boolean value, either true or false.
-   In Java, there are **four types** of **if-statements** given below.
1.  Simple if statement
2.  if-else statement
3.  if-else-if ladder
4.  Nested if-statement

Let's understand the if-statements one by one.

## 1) Simple if Statement

-   It is the most basic statement among all control flow statements in Java.
-   It evaluates a Boolean expression and enables the program to enter a block of code if the expression evaluates to true.

![](media/f6a257c0e63ae70029111743717a6e2e.png)

## 2) if-else Statement

-   The if-else statement is an extension to the if-statement, which uses another block of code, i.e., else block.
-   The else block is executed if the condition of the if-block is evaluated as false.

![](media/e260e69f0e01d5cf4ada2a55826b281d.png)

## 3) if-else-if ladder Statement

-   The if-else-if statement contains the if-statement followed by multiple else-if statements.
-   In other words, we can say that it is the chain of if-else statements that create a decision tree where the program may enter in the block of code where the condition is true.
-   We can also define an else statement at the end of the chain.

![](media/c12047f0db74099fde83215629278ae5.png)

## 4) Nested if-statement

-   In nested if-statements, the **if statement** can **contains** an **if** or **if-else** statement **inside another** **if or else-if** statement.

![](media/0565f236aabb5129cb3df6993b220a65.png)

## Switch Statement

-   In Java, Switch statements
-   are similar to if-else-if statements. The switch statement contains multiple blocks of code called cases and a single case is executed based on the variable which is being switched. The switch statement is easier to use instead of if-else-if statements. It also enhances the readability of the program.

Points to be noted about switch statement:

-   The case variables can be int, short, byte, char, or enumeration. String type is also supported since version 7 of Java
-   Cases cannot be duplicate
-   Default statement is executed when any of the case doesn't match the value of expression. It is optional.
-   Break statement terminates the switch block when the condition is satisfied.  
    It is optional, if not used, next case is executed.
-   While using switch statements, we must notice that the case expression will be of the same type as the variable. However, it will also be a constant value.

The syntax to use the switch statement is given below.

![](media/5eaaf624827539dce3fdcd070c75d1ce.png)

-   While using switch statements, we must notice that the case expression will be of the same type as the variable. However, it will also be a constant value. The switch permits only int, string, and Enum type variables to be used.

## Loop Statements

-   In programming, sometimes we need to execute the block of code repeatedly while some condition evaluates to true. However, loop statements are used to execute the set of instructions in a repeated order. The execution of the set of instructions depends upon a particular condition.
-   In Java, we have three types of loops that execute similarly. However, there are differences in their syntax and condition checking time.
1.  for loop
2.  while loop
3.  do-while loop

Let's understand the loop statements one by one.

## Java for loop

In Java, for loop

is similar to C

and C++

. It enables us to initialize the loop variable, check the condition, and increment/decrement in a single line of code. We use the for loop only when we exactly know the number of times, we want to execute the block of code.

![](media/7237c399c3785cea78fc9c43a95695f0.png)

The flow chart for the for-loop is given below.

![](media/a9ffa9e612422be5d521ed85bf3952ec.png)

## Java for-each loop

-   Java provides an enhanced for loop to traverse the data structures like array or collection. In the for-each loop, we don't need to update the loop variable. The syntax to use the for-each loop in java is given below.

![](media/672a7c3f81b91e0f1e44710979ddc883.png)

## Java while loop

-   The [while loop](https://www.javatpoint.com/java-while-loop) is also used to iterate over the number of statements multiple times. However, if we don't know the number of iterations in advance, it is recommended to use a while loop. Unlike for loop, the initialization and increment/decrement doesn't take place inside the loop statement in while loop.
-   It is also known as the entry-controlled loop since the condition is checked at the start of the loop. If the condition is true, then the loop body will be executed; otherwise, the statements after the loop will be executed.
-   The syntax of the while loop is given below.

![](media/7cda63d58122a13e184c9d14abd5dbdc.png)

The flow chart for the while loop is given in the following image.

![](media/3d8f71c59a8e403c6b17f09a470cc69f.png)

## Java do-while loop

-   The [do-while loop](https://www.javatpoint.com/java-do-while-loop) checks the condition at the end of the loop after executing the loop statements. When the number of iteration is not known and we have to execute the loop at least once, we can use do-while loop.
-   It is also known as the exit-controlled loop since the condition is not checked in advance. The syntax of the do-while loop is given below.

![](media/105ca5806ce82edd0be5bcbc4eb7e977.png)

The flow chart of the do-while loop is given in the following image.

![](media/714942e35b7815fc175aa19abf9d7645.png)

## Jump Statements

-   Jump statements are used to transfer the control of the program to the specific statements. In other words, jump statements transfer the execution control to the other part of the program. There are two types of jump statements in Java, i.e., break and continue.

## Java break statement

-   As the name suggests, the [break statement](https://www.javatpoint.com/java-break) is used to break the current flow of the program and transfer the control to the next statement outside a loop or switch statement. However, it breaks only the inner loop in the case of the nested loop.

The break statement cannot be used independently in the Java program, i.e., it can only be written inside the loop or switch statement.

## Java continue statement

-   Unlike break statement, the [continue statement](https://www.javatpoint.com/java-continue) doesn't break the loop, whereas, it skips the specific part of the loop and jumps to the next iteration of the loop immediately.

## References

1.  https://www.javatpoint.com/control-flow-in-java
