# read 1
### Responsive Overview
Responsive web design is the practice of building a website suitable to work on every device and every screen size, no matter how large or small, mobile or desktop.
### Flexible Layouts
Responsive web design is broken down into three main components, including flexible layouts, media queries, and flexible media. 

*Flexible layouts do not advocate the use of fixed measurement units, such as pixels or inches. Reason being, the viewport height and width continually change from device to device.*

`` The formula is based around taking the target width of an element and dividing it by the width of it’s parent element. The result is the relative width of the target element.
target ÷ context = result ``
* a flexible grid:capable of dynamically resizing to any width.
* Media Queries
Media queries were built as an extension to media types commonly found when targeting and including styles. Media queries provide the ability to specify different styles for individual browser and device circumstances, the width of the viewport or device orientation for example.

**Generally speaking it is recommend to use the @media rule inside of an existing style sheet to avoid any additional HTTP requests.**

`` CSS
/* @media Rule */
@media all and (max-width: 1024px) {...}
/* @import Rule */
@import url(styles.css) all and (max-width: 1024px) {...``

## float
Floats are also helpful for layout in smaller instances. Take for example this little area of a web page. If we use float for our little avatar image, when that image changes size the text in the box will reflow to accommodate:

![image](https://i1.wp.com/css-tricks.com/wp-content/csstricks-uploads/reflow-example-1.png?resize=540%2C177&ssl=1)


### Clearing the Float
![image](https://i1.wp.com/css-tricks.com/wp-content/csstricks-uploads/unclearedfooter.png?resize=540%2C195)

In the above example, the sidebar is floated to the right and is shorter than the main content area. The footer then is required to jump up into that available space as is required by the float. To fix this problem, the footer can be cleared to ensure it stays beneath both floated columns.

``#footer {
  clear: both;			
}
``


![image](https://i2.wp.com/css-tricks.com/wp-content/csstricks-uploads/clearedfooter.png?resize=540%2C230)

### Techniques for Clearing Floats
  1. The Empty Div Method is, quite literally, an empty div.

  ``<div style="clear: both;"></div>``. Sometimes you’ll see a <br> element or some other random element used, but div is the most common because it has no browser default styling, doesn’t have any special function, and is unlikely to be generically styled with CSS. 

 2. The Overflow Method relies on setting the overflow CSS property on a parent element. If this property is set to auto or hidden on the parent element, the parent will expand to contain the floats, effectively clearing it for succeeding elements. This method can be beautifully semantic as it may not require additional elements. However if you find yourself adding a new div just to apply this, it is equally as non-semantic as the empty div method and less adaptable.
 3. The Easy Clearing Method uses a clever CSS pseudo selector (:after) to clear floats. Rather than setting the overflow on the parent, you apply an additional class like “clearfix” to it. Then apply this CSS:

 ``
.clearfix:after { 
   content: "."; 
   visibility: hidden; 
   display: block; 
   height: 0; 
   clear: both;
}``

This will apply a small bit of content, hidden from view, after the parent element which clears the float. This isn’t quite the whole story, as additional code needs to be used to accommodate for older browsers.

## Grid
A block level element is as wide as the parent it’s inside (width: auto;). We can think of it as 100% wide. The wrapper for a grid probably don’t have much to do with semantics, it’s just a generic wrapper, so a div is fine.

Columns
Let’s start with a practical and common need: a main content area being 2/3 the width and a sidebar being 1/3 the width. We just make two column divs with appropriate class names.

```<div class="grid">
  <div class="col-2-3">
     Main Content
  </div>
  <div class="col-1-3">
     Sidebar
  </div>
 </div>
 ```
To make them next to each other, we just need to float them and apply widths. We can select both like this:

```
[class*='col-'] {
  float: left;
}
and individual width like this:

.col-2-3 {
  width: 66.66%;
}
.col-1-3 {
  width: 33.33%;
}

That’s the whole premise of not overthinking grids.

Clearing Context
The parent element will collapse to zero height since it has only floated children. Let’s fix that by clearing it. These days all you need is this:

.grid:after {
  content: "";
  display: table;
  clear: both;
}
```



###  Gutters
1. The first step toward this is using box-sizing: border-box(Now when we set a width, that element stays that width, despite padding or borders being applied.)
2. The second step is applying a fixed padding to the right side of all columns except the last one.
```
[class*='col-'] {
  padding-right: 20px;
}
[class*='col-']:last-of-type {
  padding-right: 0;
}
```

* ***Note:A CSS pseudo-element is a keyword added to a selector that lets you style a specific part of the selected element(s). For example, ::first-line can be used to change the font of the first line of a paragraph.***
* ***Note: CSS3 introduced the ::after notation (with two colons) to distinguish pseudo-classes from pseudo-elements. Browsers also accept :after, introduced in CSS2.***
* ***note:the clear property. “Clear” allows elements to specify where they should align in comparison to the floated elements.***

## SMACSS 
 SMACSS is a way to examine your design process and as a way to fit those rigid frameworks into a flexible thought process. It is an attempt to document a consistent approach to site development when using CSS. And really, who isn’t building a site with CSS these days?!






