# Constructor Chaining

**Content**

1\. Constructor Chaining in Java

1.1 Why do We Need Constructor Chaining?

1.2 Rules for Constructor Chaining

2 Ways to Implement Java Constructor Chaining

2.1 Constructor Chaining Within the Same Class:

2.2 Constructor Chaining from Parent/Base Class:

3\. References

## 1. Constructor Chaining in Java

-   Constructor chaining is the process of invoking a series of constructors within the same class or by the child class's constructors.
-   In Java programming, constructor chaining generally happens as a result of the Inheritance process.
-   When we are chaining constructors in a Java program, the first line of a constructor should always start with either this() or super() method according to the type of constructor chaining we want to implement.
-   We use this() method to call a constructor from another overloaded constructor in the same class, and the super() method to invoke an immediate parent class constructor.

## 1.1 Why do We Need Constructor Chaining?

-   If we want to instantiate objects of a class with different types or numbers of parameters, we require different constructor definitions in the class. These different constructors can be made efficiently using constructor chaining.
-   Constructor chaining in Java enables us to define various constructors for each task and connect them with links or chains to improve the quality of the code.
-   If we don't chain constructors together and one of them requires a certain parameter, we'll have to initialize that parameter twice in each constructor.

## 1.2 Rules for Constructor Chaining

If we wish to use constructor chaining in Java, we have to follow the below guidelines:

-   The constructor's definition should always start with the this() or super() method as the initial statement.
-   There should be at least one constructor in the class that does not include this() method.
-   The constructor chaining can be performed in any sequence.

## 2 Ways to Implement Java Constructor Chaining

-   There are two ways in which constructor chaining is performed in Java, let's see the two ways below:

## 2.1 Constructor Chaining Within the Same Class:

-   We make several constructors with a different number of parameters (or with the different data types of parameters) within the same class and make a chain with these constructors using the this() method.
-   we use this() method to call a constructor from another overloaded constructor in the same class.

**Example:**

```java
class Main {
    public static void main(String args[]) {
        Employee employee = new Employee(); // calling the 1st constructor
        System.out.println("Employee Name: " + employee.getName());
        System.out.println("Employee ID: " + employee.getEmpID());
    }
}

class Employee{

    private String name;
    private int empID;
    
    // 1st constructor
    public Employee() {
        this("NULL"); // calling the 2nd constructor
    }
    
    // 2nd constructor
    public Employee(String name) {
        this(name, 0); // calling the 3rd constructor
    }
    
    // 3rd constructor
    public Employee(String name, int empID) { // fully parameterized constructor
        this.name = name;
        this.empID = empID;
    }
    
    public String getName() {
        return name;
    }
    
    public int getEmpID() {
        return empID;
    }
}
```

**Output:**

```
Employee Name: NULL
Employee ID: 0
```

-   We can understand from the above example that when we created an object employee of the Employee class, it invoked a constructor with zero parameters as we have not passed any parameters while instantiating the employee object.
-   In the first constructor, we have used this("NULL"); method as the initial statement, which invoked the second constructor with one parameter.
-   In the second constructor, we have used this(name, 0); (name contains NULL string from the first constructor) as the initial statement, which invoked the third constructor with two parameters.
-   The third constructor initialized the employee object with name containing NULL and empID containing 0.
-   This series of invoking constructors from other constructors is known as constructor chaining within the same class.

## 2.2 Constructor Chaining from Parent/Base Class:

-   The objective of a sub-class constructor is to invoke the parent class's constructor first.
-   This ensures that the initialization of the parent class's fields or member variables is performed as the first step in the creation of the sub-class's object.
-   In Java, inheritance chains can contain any number of classes, every sub-class constructor calls up the constructor of the immediate parent class (using the super() method) in a chain until it reaches the top-level class.

**Example:**

```java
class Main {
    public static void main(String args[]) {
        WagonR car1 = new WagonR("WagonR 2022", "Automobile", 4, 4, 5);
        System.out.println("Vehicle name: " + car1.getName());
        System.out.println("Vehicle type: " + car1.getType());
        System.out.println("Car doors: " + car1.getDoors());
        System.out.println("Car wheels: " + car1.getWheels());
        System.out.println("WagonR seats: " + car1.getSeats());
    }
}

class Vehicle{
    private String name;
    private String type;
    
    public Vehicle(String name, String type) {
        this.name = name;
        this.type = type;
        System.out.println("Vehicle constructor invoked!");
    }
    
    public String getName() {
        return name;
    }
    
    public String getType() {
        return type;
    }
}
class Car extends Vehicle {

    private int doors;
    private int wheels;
    
    public Car(String name, String type, int doors, int wheels) {
        super(name, type); // Vehicle class constructor is called
        this.doors = doors;
        this.wheels = wheels;
        System.out.println("Car constructor invoked!");
    }
    
    public int getDoors() {
        return doors;
    }
    
    public int getWheels() {
        return wheels;
    }
}

class WagonR extends Car {
    private int seats;
    
    public WagonR(String name, String type, int doors, int wheels, int seats) {
        super(name, type, doors, wheels); // Car class constructor is called
        this.seats = seats;
        System.out.println("WagonR constructor invoked!");
    }
    
    public int getSeats() {
        return seats;
    }
}
```

**Output:**

```
Vehicle constructor invoked!
Car constructor invoked!
WagonR constructor invoked!
Vehicle Name: WagonR 2022
Vehicle type: Automobile
Car doors: 4
Car wheels: 4
WagonR seats: 5
```

**Explanation:**

-   We have created a WagonR class that extends the Car class which also extends the Vehicle class, having certain fields defined in each class.
-   We can understand from the above exmple that when we created an object car1 of WagonR class, it invoked the WagonR class constructor.
-   In the WagonR class constructor, we have used super(name, type, doors, wheels); method (doors and wheels contains 4 passed from the WagonR constructor instantiation) as the initial statement, which invoked the Car class constructor initializing doors and wheels fields,
-   In the Car class constructor, we have used super(name, type); method (name contains WagonR 2022 string and type contains Automobile string passed from the Car constructor), which invoked the Vehicle class constructor initializing name and type fields.
-   The Vehicle class (Top-level) constructor is the first fully executed constructor and after that rest of the code in Car and WagonR constructors is executed respectively. This type of constructor chaining helps in initializing all the fields related to an object in one go.

## 3. References

https://www.scaler.com/topics/constructor-chaining-in-java/
