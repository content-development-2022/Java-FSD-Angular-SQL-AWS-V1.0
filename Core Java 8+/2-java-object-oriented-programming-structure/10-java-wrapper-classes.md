# Java Wrapper Classes

**Content**

1\. Wrapper Classes

1.1 Creating Wrapper Objects

2\. References

## 1. Wrapper Classes

-   The eight primitive data types byte, short, int, long, float, double, char and boolean are not objects, **Wrapper classes are used for converting primitive data types into objects.**
-   The table below shows the primitive type and the equivalent wrapper class:

![](media/4b45b88dd3e7f552e63814a6b8f7e1cf.png)

-   Sometimes you must use wrapper classes, for example when working with Collection objects, such as ArrayList, where primitive types cannot be used (the list can only store objects):

**Example**

![](media/d7b3d68bed63fe327d75e1052b7e8481.png)

## 1.1 Creating Wrapper Objects

-   To create a wrapper object, use the wrapper class instead of the primitive type.
-   To get the value, you can just print the object:

**Example-1:**

![](media/0dfec0df31729bb85615e52ec5ecd8ef.png)

**Output:**

![](media/28039c0a06538e2e23e19790e385d6e7.png)

-   Since you're now working with objects, you can use certain methods to get information about the specific object.
-   For example, the following methods are used to get the value associated with the corresponding wrapper object: intValue(), byteValue(), shortValue(), longValue(), floatValue(), doubleValue(), charValue(), booleanValue().
-   This example will output the same result as the example above:

**Example-2:**

![](media/f958aa3c4fd57b4c5d5543b2ea2b9a21.png)

**Output:**

![](media/28c17da75dc7c152a810feb9e3fc2fe6.png)

-   Another useful method is the **toString()** method, which is used to convert wrapper objects to strings.
-   In the following example, we convert an Integer to a String, and use the length() method of the String class to output the length of the "string".

**Example-3:**

![](media/dcb49015edc0124df20371662266d02a.png)

**Output:**

![](media/a45688217e7111c263c0b3780f4256ca.png)

## 2. References

1\. https://www.w3schools.com/java/java_wrapper_classes.asp
