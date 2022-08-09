Grid Layout

The CSS Grid Layout Module offers a grid-based layout system, with rows and columns, making it easier to design web pages without having to use floats and positioning.

## Grid Elements

A grid layout consists of a parent element, with one or more child elements.

### Example

\<div class="grid-container"\>  
\<div class="grid-item"\>1\</div\>  
\<div class="grid-item"\>2\</div\>  
\<div class="grid-item"\>3\</div\>  
\<div class="grid-item"\>4\</div\>  
\<div class="grid-item"\>5\</div\>  
\<div class="grid-item"\>6\</div\>  
\<div class="grid-item"\>7\</div\>  
\<div class="grid-item"\>8\</div\>  
\<div class="grid-item"\>9\</div\>  
\</div\>

![](media/241a229f527213cd7dad2bdfd6d1297b.png)

## Display Property

An HTML element becomes a grid container when its display property is set to grid or inline-grid.

### Example

.grid-container {  
 display: grid;  
}

### Example

.grid-container {  
 display: inline-grid;  
}

All direct children of the grid container automatically become *grid items*.

## Grid Columns

The vertical lines of grid items are called *columns*.

## ![](media/c289861bcf42ec50c0b4c8e45ebe8385.png)

## Grid Rows

The horizontal lines of grid items are called *rows*.

![](media/5d5fafc0f3e2ca85db71b4682dffa340.png)
