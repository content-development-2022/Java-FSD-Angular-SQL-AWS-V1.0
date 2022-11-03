# Class Math

**Content**

1\. Class Math

1.1 Math Method

2\. References

## 1. Class Math

-   The class Math contains methods for performing basic numeric operations such as the elementary exponential, logarithm, square root, and trigonometric functions.

## 1.1 Math Method

## 1) floor

>   `public static double floor(double a)`

**Parameters:**

a - a value.

**Returns:**

-   The largest (closest to positive infinity) floating-point value that less than or equal to the argument and is equal to a mathematical integer.

**Special cases:**

-   If the argument value is already equal to a mathematical integer, then the result is the same as the argument.
    -   If the argument is NaN or an infinity or positive zero or negative zero, then the result is the same as the argument.

## 2) max

>   `public static double max(double a, double b)`

**Parameters:**

a - an argument.

b - another argument.

**Returns:**

the larger of a and b.

-   If the arguments have the same value, the result is that same value.
-   If either value is NaN, then the result is NaN.
-   Unlike the numerical comparison operators, this method considers negative zero to be strictly smaller than positive zero.
-   If one argument is positive zero and the other negative zero, the result is positive zero.

## 3) min

>   `public static int min(int a, int b)`

**Parameters:**

a - an argument.

b - another argument.

**Returns:**

the smaller of a and b.

-   If the arguments have the same value, the result is that same value.

## 4) pow

>   `public static double pow(double a, double b)`

**Parameters:**

a - the base.

b - the exponent.

**Returns:**

The value ab.

Returns the value of the first argument raised to the power of the second argument. Special cases:

-   If the second argument is positive or negative zero, then the result is 1.0.
    -   If the second argument is 1.0, then the result is the same as the first argument.
    -   If the second argument is NaN, then the result is NaN.
    -   If the first argument is NaN and the second argument is nonzero, then the result is NaN.
    -   If
        -   the absolute value of the first argument is greater than 1 and the second argument is positive infinity, or
        -   the absolute value of the first argument is less than 1 and the second argument is negative infinity,

            then the result is positive infinity.

    -   If
        -   the absolute value of the first argument is greater than 1 and the second argument is negative infinity, or
        -   the absolute value of the first argument is less than 1 and the second argument is positive infinity,

            then the result is positive zero.

    -   If the absolute value of the first argument equals 1 and the second argument is infinite, then the result is NaN.
    -   If
        -   the first argument is positive zero and the second argument is greater than zero, or
        -   the first argument is positive infinity and the second argument is less than zero,

            then the result is positive zero.

    -   If
        -   the first argument is positive zero and the second argument is less than zero, or
        -   the first argument is positive infinity and the second argument is greater than zero,

            then the result is positive infinity.

    -   If
        -   the first argument is negative zero and the second argument is greater than zero but not a finite odd integer, or
        -   the first argument is negative infinity and the second argument is less than zero but not a finite odd integer,

            then the result is positive zero.

    -   If
        -   the first argument is negative zero and the second argument is a positive finite odd integer, or
        -   the first argument is negative infinity and the second argument is a negative finite odd integer,

            then the result is negative zero.

    -   If
        -   the first argument is negative zero and the second argument is less than zero but not a finite odd integer, or
        -   the first argument is negative infinity and the second argument is greater than zero but not a finite odd integer,

            then the result is positive infinity.

    -   If
        -   the first argument is negative zero and the second argument is a negative finite odd integer, or
        -   the first argument is negative infinity and the second argument is a positive finite odd integer,

            then the result is negative infinity.

    -   If the first argument is finite and less than zero
        -   if the second argument is a finite even integer, the result is equal to the result of raising the absolute value of the first argument to the power of the second argument
        -   if the second argument is a finite odd integer, the result is equal to the negative of the result of raising the absolute value of the first argument to the power of the second argument
        -   if the second argument is finite and not an integer, then the result is NaN.
    -   If both arguments are integers, then the result is exactly equal to the mathematical result of raising the first argument to the power of the second argument if that result can in fact be represented exactly as a double value.

(In the foregoing descriptions, a floating-point value is considered to be an integer if and only if it is finite and a fixed point of the method ceil or, equivalently, a fixed point of the method floor. A value is a fixed point of a one-argument method if and only if the result of applying the method to the value is equal to the value.)

-   The computed result must be within 1 ulp of the exact result. Results must be semi-monotonic.

## 5) round

>   `public static int round(float a)`

**Parameters:**

a - a floating-point value to be rounded to an integer.

**Returns:**

the value of the argument rounded to the nearest int value.

**Special cases:**

-   If the argument is NaN, the result is 0.
    -   If the argument is negative infinity or any value less than or equal to the value of Integer.MIN_VALUE, the result is equal to the value of Integer.MIN_VALUE.
    -   If the argument is positive infinity or any value greater than or equal to the value of Integer.MAX_VALUE, the result is equal to the value of Integer.MAX_VALUE.

## 6) random

>   `public static double random()`

**Returns:**

a pseudorandom double greater than or equal to 0.0 and less than 1.0.

The positive square root of a. If the argument is NaN or less than zero, the result is NaN.

-   Returns a double value with a positive sign, greater than or equal to 0.0 and less than 1.0. Returned values are chosen pseudorandomly with (approximately) uniform distribution from that range.
-   When this method is first called, it creates a single new pseudorandom-number generator, exactly as if by the expression

    new java.util.Random()

-   This new pseudorandom-number generator is used thereafter for all calls to this method and is used nowhere else.
-   This method is properly synchronized to allow correct use by more than one thread. However, if many threads need to generate pseudorandom numbers at a great rate, it may reduce contention for each thread to have its own pseudorandom-number generator.

## 7) sqrt

>   `public static double sqrt(double a)`

**Parameters:**

a – a value

**Returns:**

Returns the correctly rounded positive square root of a double value.

**Special cases:**

-   If the argument is NaN or less than zero, then the result is NaN.
    -   If the argument is positive infinity, then the result is positive infinity.
    -   If the argument is positive zero or negative zero, then the result is the same as the argument.

Otherwise, the result is the double value closest to the true mathematical square root of the argument value.

## 8) abs

>   `public static int abs(int a)`

**Parameters:**

a - the argument whose absolute value is to be determined

**Returns:**

The absolute value of the argument.

-   If the argument is not negative, the argument is returned. If the argument is negative, the negation of the argument is returned.

**Note** that if the argument is equal to the value of Integer. MIN_VALUE, the most negative representable int value, the result is that same value, which is negative.

-   To know more information about math methods [click here](https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html#floor-double-).

## 2. References

1.  https://docs.oracle.com/javase/8/docs/api/java/lang/Math.html
