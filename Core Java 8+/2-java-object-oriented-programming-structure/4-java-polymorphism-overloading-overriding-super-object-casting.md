# Java Polymorphism, Method Overloading and Method Overriding

**Content**

1\. Polymorphism

2\. Types of Polymorphism

2.1 Compile-Time Polymorphism /Static/Method Overloading

2.1.1 Different ways to Overload the Methods

2.1.2 Operator overloading

2.1.3 Advantages of compile-time polymorphism:

2.2 Run-Time Polymorphism/Dynamic/Method Overriding

2.2.1 Rules for method overriding

2.2.2 Difference between Method Overloading and Method Overriding in Java

3\. super Keyword in Java

4\. Object Typecasting

4.1 Upcasting

4.2 Downcasting

4.3 Why we need Upcasting and Downcasting?

4.4 Difference between Upcasting and Downcasting

5\. References

## 1. Polymorphism

-   Polymorphism is one of the OOPs feature that allows us to perform a single action in different ways.
-   Polymorphism means "many forms", and it occurs when we have many classes that are related to each other by inheritance.
-   **For example**, think of a superclass called **Animal** that has a method called **animalSound().** Subclasses of Animals could be Pigs, Cats, Dogs, Birds - And they also have their own implementation of an animal sound (the pig oinks, and the cat meows, etc.).

    ![](media/2ba89566a6a42343a29d2cbc2a79365b.png)

    **Output:**

    ![](media/e1ec58f96b90a87474c1ca2cee4872ee.png)

## 2. Types of Polymorphism

There are two types of polymorphism in java:

1.  **Static Polymorphism** also known as compile time polymorphism
2.  **Dynamic Polymorphism** also known as runtime polymorphism

**Note:** Run time polymorphism is implemented through Method overriding. Whereas, Compile Time polymorphism is implemented through Method overloading and Operator overloading.

## 2.1 Compile-Time Polymorphism /Static/Method Overloading

-   Compile-time polymorphism is a polymorphism that is resolved during the compilation process.
-   Overloading of methods is called through the reference variable of a class.
-   Compile-time polymorphism is achieved by **method overloading**
-   Method Overloading occurs when a class has many methods with the same name but different parameters.
-   Two or more methods may have the same name if they have other numbers of parameters, different data types, or different numbers of parameters and different data types.
-   Method overloading is also known as **Compile-time Polymorphism, Static Polymorphism, or** **Early binding** in Java.

**Example of Compile-Time Polymorphism in Java**

![](media/1fd109260b70e46068a1f768dd4abb92.png)

**Output:**

Sum of two numbers: 120

Sum of three numbers: 147

-   In this program, the sum() method overloads with two types via different parameters.
-   This is the basic concept of compile-time polymorphism in java where we can perform various operations by using multiple methods having the same name.

**Another Example:**

![](media/802dc446d947a1078a2e221758041a99.png)

**Output:**

![](media/842ed3f3aa868ae1dbfb1190a6532da3.png)

## 2.1.1 Different ways to Overload The Methods

**1). Method overloading by changing the number of parameters**

-   In this type, Method overloading is done by overloading methods in the function call with a varied number of parameters

**Example:**

![](media/0e3affdb94b10e5ecef8775eefeadda2.png)

-   In the given example, the first show method has one parameter, and the second show method has two methods.
-   When a function is called, the compiler looks at the number of parameters and decides how to resolve the method call.

**2). Method overloading by changing datatype of parameter**

-   In this type, Method overloading is done by overloading methods in the function call with different types of parameters

**Example:**

![](media/d791a3fee0a0ffa9ed437839c472dc28.png)

-   In the above example, the first show method has two float parameters, and the second show method has two int parameters.
-   When a function is called, the compiler looks at the data type of input parameters and decides how to resolve the method call.

**3). By changing the** **sequence of parameters**

-   In this type, overloading is dependent on the sequence of the parameters

**Example:**

![](media/23e1fafed27f685978ecea6543dc02ff.png)

-   In this example, The parameters int and float are used in the first declaration.
-   The parameters are int and float in the second declaration, but their order in the parameter list is different.

## 2.1.1.2 Invalid cases of method overloading

-   Method overloading does not allow **changing the** **return type of method**( function ); it occurs ambiguity.

**Examples**

![](media/a1e9fc84e588398f5682f1ac07ea7f28.png)

-   Because the arguments are matching, the code above will not compile.
-   Both methods have the same amount of data types and the same sequence of data types in the parameters.

## 2.1.2 Operator overloading

-   An operator is said to be overloaded if it can be used to perform more than one function.
-   Operator overloading is an overloading method in which an existing operator is given a new meaning.
-   In Java, the + operator is overloaded.
-   **Java, on the other hand, does not allow for user-defined operator overloading.**

**Example:**

![](media/07f181421624894a3534b94cfdeb6562.png)

-   In the above example, The ‘+’ operator has been overloaded.
-   When we send two numbers to the overloaded method, we get a sum of two integers, and when we pass two Strings, we get the concatenated text.

## 2.1.3 Advantages of compile-time polymorphism:

1.  It improves code clarity and allows for the use of a single name for similar procedures.
2.  It has a faster execution time since it is discovered early in the compilation process.

The only **disadvantage** of compile-time polymorphism is that it doesn’t include inheritance.

## 2.2 Run-Time Polymorphism/Dynamic/Method Overriding

-   Whenever an object is bound with the functionality at run time, this is known as runtime polymorphism.
-   Java virtual machine determines the proper method to call at the runtime, not at the compile time.
-   It is also called **dynamic or late binding**.
-   The runtime polymorphism can be achieved by **method overriding**.
-   In any object-oriented programming language, Overriding is a feature that allows a subclass or child class to provide a specific implementation of a method that is already provided by one of its super-classes or parent classes.
-   When a method in a subclass has the same name, same parameters or signature, and same return type(or sub-type) as a method in its super-class, then the method in the subclass is said to *override* the method in the super-class.

![](media/cacf581ea9ca6f004e590465190fdc5d.png)

## 2.2.1 Rules for method overriding

1.  There must be an IS-A relationship (inheritance).
2.  The access modifier can only allow more access for the overridden method.
3.  A final method does not support method overriding.
4.  A static method cannot be overridden.
5.  Private methods cannot be overridden.
6.  The return type of the overriding method must be the same.
7.  We can call the parent class method in the overriding method using the super keyword.
8.  A constructor cannot be overridden because a child class and a parent class cannot have the constructor with the same name.

**Example:**

![](media/105de6c8a73cdabfb05b8d03ea343223.png)

**Output:**

![](media/8d582e03f3565ffefe94897420f6a847.png)

## 2.2.2 Difference between Method Overloading and Method Overriding in Java

![](media/6ff72fa230ee9d4a58c8eb3e0104c0de.png)

## 3. super Keyword in Java

-   The **super is a** keyword in Java which is used to refer immediate parent class object.
-   Whenever you create the instance of subclass, an instance of parent class is created implicitly.

**Usage of Java super Keyword**

![](media/usage-super-keyword.png)

## 3.1 super is used to refer immediate parent class instance variable.

-   We can use super keyword to access the data member or field of parent class.
-   It is used if parent class and child class have same fields.

**Example:**

```
class Animal {
    String color="white";
}

class Dog extends Animal {
    String color="black";
    void printColor() {
        System.out.println(color);//prints color of Dog class
        System.out.println(super.color);//prints color of Animal class
    }
}

class TestSuper1 {
    public static void main(String args[]) {
        Dog d=new Dog();
        d.printColor();
    }
}
```

**Output:**

```
black

white
```

-   In the above example, Animal and Dog both classes have a common property color.
-   If we print color property, it will print the color of current class by default.
-   To access the parent property, we need to use super keyword.

## 3.2 super can be used to invoke parent class method

-   The super keyword can also be used to invoke parent class method.
-   It should be used if subclass contains the same method as parent class.
-   In other words, it is used if method is overridden.

**Example:**

```
class Animal {
        void eat() {  
        System.out.println("eating...");     
        }
}

class Dog extends Animal{
    void eat() {
        System.out.println("eating bread...");       
    }
   void bark() {       
        System.out.println("barking...");            
    }  
    void work() {
        super.eat();
        bark();
    }
}

class TestSuper2 {
    public static void main(String args[]){
        Dog d=new Dog();
        d.work();
    }
}
```

**Output:**

```
eating...

barking...
```

-   In the above example Animal and Dog both classes have eat() method if we call eat() method from Dog class, it will call the eat() method of Dog class by default because priority is given to local.
-   To call the parent class method, we need to use super keyword.

## 3.3 super is used to invoke parent class constructor.

-   The super keyword can also be used to invoke the parent class constructor.

**Example:**

```
class Animal {
    Animal() {
        System.out.println("animal is created");
    }
}

class Dog extends Animal {
    Dog() {
        super();
        System.out.println("dog is created");
    }
}

class TestSuper3 {
    public static void main(String args[]) {
        Dog d=new Dog();
    }  
}
```

**Output:**

```
animal is created

dog is created
```

**Note:**

-   super() is added in each class constructor automatically by compiler if there is no super() or this().

![](media/compiler-super.png)

-   As we know well that default constructor is provided by compiler automatically if there is no constructor. But, it also adds super() as the first statement.

## 4. Object Typecasting

-   A process of converting one data type to another is known as **Typecasting**.
-   In Java, the object can also be typecasted like the datatypes.
-   Parent and Child objects are two types of objects.
-   So, there are two types of typecasting possible for an object, i.e., **Parent to Child** and **Child to Parent** or can say **Upcasting** and **Downcasting**.
-   Typecasting is used to ensure whether variables are correctly processed by a function or not.
-   In Upcasting and Downcasting, we typecast a child object to a parent object and a parent object to a child object simultaneously.
-   We can perform Upcasting implicitly or explicitly, but downcasting cannot be implicitly possible.

![](media/0371286d114702bc45c08c71350d85c7.png)

## 4.1 Upcasting

-   Upcasting is a type of object typecasting in which a **child object** is typecasted to a **parent class object**.
-   By using the Upcasting, we can easily access the variables and methods of the parent class to the child class.
-   Here, we don't access all the variables and the method.
-   We access only some specified variables and methods of the child class.
-   Upcasting is also known as **Generalization** and **Widening**.

**Example:**

![](media/c30f1d068789794092e8c3398c809d69.png)

**Output:**

![](media/520190185ce12afce2df4788177c3820.png)

## 4.2 Downcasting

-   **Downcasting** is another type of object typecasting.
-   In Downcasting, we assign a parent class reference object to the child class.
-   In Java, we cannot assign a parent class reference object to the child class, but if we perform downcasting, we will not get any compile-time error.
-   However, when we run it, it throws the **"ClassCastException"**.
-   Now the point is if downcasting is not possible in Java, then why is it allowed by the compiler? In Java, some scenarios allow us to perform downcasting.
-   Below is an example of downcasting in which both the valid and the invalid scenarios are explained:

**Example:**

![](media/27bbee68f45efa4010939141e1b582a4.png)

**Output:**

![](media/7e2482b6f6413b0c698f154633da19b3.png)

## 4.3 Why we need Upcasting and Downcasting?

-   In Java, we rarely use **Upcasting**. We use it when we need to develop a code that deals with only the parent class.
-   **Downcasting** is used when we need to develop a code that accesses behaviors of the child class.

![](media/c44708b1be9ed561fe3a4340298c1a4b.png)

## 4.4 Difference between Upcasting and Downcasting

-   These are the following differences between Upcasting and Downcasting:

![](media/a43441aed780c36e90ad48c3beb8815a.png)

## 5. References

1.  https://www.mygreatlearning.com/blog/polymorphism-in-java/
2.  https://www.tutorialspoint.com/Runtime-Polymorphism-in-Java
3.  https://www.javatpoint.com/super-keyword
4.  https://www.javatpoint.com/upcasting-and-downcasting-in-java
