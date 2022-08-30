## CSS Media Queries, Animations, Flexbox

**Content**

1\. CSS Media Queries

2\. CSS Animations

2.1 What are CSS Animations?

2.2 The @keyframes Rule

3\. CSS Flexbox Layout Module

4\. References

# 1. CSS Media Queries

**CSS2 Introduced Media Types**

-   The @media rule, introduced in CSS2, made it possible to define different style rules for different media types.
-   **Examples:** You could have one set of style rules for computer screens, one for printers, one for handheld devices, one for television-type devices, and so on.
-   Unfortunately these media types never got a lot of support by devices, other than the print media type.

**CSS3 Introduced Media Queries**

-   Media queries in CSS3 extended the CSS2 media types idea: Instead of looking for a type of device, they look at the capability of the device.
-   Media queries can be used to check many things, such as:
1.  width and height of the viewport
2.  width and height of the device
3.  orientation (is the tablet/phone in landscape or portrait mode?)
4.  resolution
-   Media queries are a popular technique for delivering a tailored style sheet to desktops, laptops, tablets, and mobile phones (such as iPhone and Android phones).
-   To know more details about Media queries [Clickhere](https://www.w3schools.com/css/css3_mediaqueries.asp)

## 2. CSS Animations

-   CSS allows animation of HTML elements without using JavaScript or Flash!
-   the following are the animation properties:
1.  @keyframes
2.  animation-name
3.  animation-duration
4.  animation-delay
5.  animation-iteration-count
6.  animation-direction
7.  animation-timing-function
8.  animation-fill-mode
9.  animation

## 2.1 What are CSS Animations?

-   An animation lets an element gradually change from one style to another.
-   You can change as many CSS properties you want, as many times as you want.
-   To use CSS animation, you must first specify some keyframes for the animation.
-   Keyframes hold what styles the element will have at certain times.

## 2.2 The @keyframes Rule

-   When you specify CSS styles inside the @keyframes rule, the animation will gradually change from the current style to the new style at certain times.
-   To get an animation to work, you must bind the animation to an element.
-   The following example binds the "example" animation to the \<div\> element. The animation will last for 4 seconds, and it will gradually change the background-color of the \<div\> element from "red" to "yellow":

**Example**

/\* The animation code \*/  
@keyframes example {  
from {background-color: red;}  
to {background-color: yellow;}  
}

/\* The element to apply the animation to \*/  
div {  
width: 100px;  
height: 100px;  
background-color: red;  
animation-name: example;  
animation-duration: 4s;  
}

**Note:**

-   The animation-duration property defines how long an animation should take to complete. If the animation-duration property is not specified, no animation will occur, because the default value is 0s (0 seconds).
-   In the example above we have specified when the style will change by using the keywords "from" and "to" (which represents 0% (start) and 100% (complete)).
-   To know more details about animation [Clickhere](https://www.w3schools.com/css/css3_animations.asp)

## 3. CSS Flexbox Layout Module

-   Before the Flexbox Layout module, there were four layout modes:
1.  Block, for sections in a webpage
2.  Inline, for text
3.  Table, for two-dimensional table data
4.  Positioned, for explicit position of an element
-   The Flexible Box Layout Module, makes it easier to design flexible responsive layout structure without using float or positioning.
-   To know more details about flex [Clickhere](https://www.w3schools.com/css/css3_flexbox.asp)

## 4. References

1.  https://www.w3schools.com/css/css3_mediaqueries.asp
2.  https://www.w3schools.com/css/css3_flexbox.asp
3.  https://www.w3schools.com/css/css3_animations.asp
