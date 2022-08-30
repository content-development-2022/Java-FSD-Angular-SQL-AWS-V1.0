## CSS Combinators

**Content**

1\. CSS Combinators

1.1 Descendant Selector

1.2 Child Selector (\>)

1.3 Adjacent Sibling Selector (+)

1.4 General Sibling Selector (\~)

2\. References

## 1. CSS Combinators

-   A combinator is something that explains the relationship between the selectors.
-   A CSS selector can contain more than one simple selector. Between the simple selectors, we can include a combinator.

There are four different combinators in CSS:

-   descendant selector (space)
-   child selector (\>)
-   adjacent sibling selector (+)
-   general sibling selector (\~)

## 1.1 Descendant Selector

-   The descendant selector matches all elements that are descendants of a specified element.
-   The following example selects all \<p\> elements inside \<div\> elements:

**Example**

div p {  
background-color: yellow;  
}

## 1.2 Child Selector (\>)

-   The child selector selects all elements that are the children of a specified element.
-   The following example selects all \<p\> elements that are children of a \<div\> element:

**Example**

div \> p {  
background-color: yellow;  
}

## 1.3 Adjacent Sibling Selector (+)

-   The adjacent sibling selector is used to select an element that is directly after another specific element.
-   Sibling elements must have the same parent element, and "adjacent" means "immediately following".
-   The following example selects the first \<p\> element that are placed immediately after \<div\> elements:

**Example**

div + p {  
background-color: yellow;  
}

## 1.4 General Sibling Selector (\~)

-   The general sibling selector selects all elements that are next siblings of a specified element.
-   The following example selects all \<p\> elements that are next siblings of \<div\> elements:

**Example**

div \~ p {  
background-color: yellow;  
}

## 2. References

1.  https://www.w3schools.com/css/css_combinators.asp
