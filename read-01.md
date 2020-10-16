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
  1. The Empty Div Method is, quite literally, an empty div. <div style="clear: both;"></div>. Sometimes you’ll see a <br> element or some other random element used, but div is the most common because it has no browser default styling, doesn’t have any special function, and is unlikely to be generically styled with CSS. 

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




