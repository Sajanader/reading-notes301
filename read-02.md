# read 02
## Why pair program?
1. Greater efficiency
2. Engaged collaboration
3. Learning from fellow students
4. Social skills
5. Job interview readiness
6. Work environment readiness

## jQuery 
offers a simple way to achieve a variety of common JavaScript tasks quickly and consistently, across all major browsers and without any fallback code needed.
**example**
```
$(' :header').addClass('headline');
@ $(' l i : lt(3) ').hide(). fadeln(lSOO);
$('li').on('click', function() {
$(this) . remove();
} );
```


## WHY USE JQUERY?
jQuery doesn't do anything you cannot achieve with pure JavaScript.
It is just a JavaScript file but estimates show it has been used on over a
quarter of the sites on the web, because it makes coding simpler. 

**. html()**
When this method is used to retrieve information
from a jQuery selection, it retrieves only the HTML
inside the first element in the matched set, along
with any of its descendants.
For example, ```$ (' u l ' ) • html () ; will return this:```
```
<li id="one"><em>fresh</em> figs</li>
<l i id="two">pine nuts</li>
<li id="three">honey</li>
<l i id="four">balsamic vinegar</l i>
Whereas $ ( 'l i ') .html (); will return this:
<em>fresh</em> figs 
```
***. text()***

When this method is used to retrieve the text from
a jQuery selection, it returns the content from every
element in the jQuery selection, along with the text
from any descendants.
For example,
``` $ ( ' u l ') . text () ; will return this:
fresh figs
pine nuts
honey
balsamic vint;!gar
Whereas $ ( 'l i ') . text () ; will return this:
fresh figspine nutshoneybalsamic vinegar 
```

### example 

**JAVASCRIPT** 
```
var $listHTML = ${'ul') . html(};
$ ( 'ul '). append($1 i stHTML);
The selector returns the <u l > element. The • html () method gets all the
HTML inside it (the four <1 i> elements). This is then appended to the
end of the selection, in this case after the existing <1 i >elements.
```
**JAVASCRIPT**

```
var $1istText = $('ul').text();
${'ul ') . append('<p>' + $listText + 1
</ p>');
The selector returns the <u 1 > element. The . text() method gets the
text from all of the <ul >element's children. This is then appended to the
end of the selection, in this case after the existing <ul >element.
```

**JAVASCRIPT**

```
var $1 i stltemHTML = $ ( '1 i ') . html() ;
$('1i ') . append{'<i>' + $1istltemHTML + '</ i>') ;
The selector returns the four <1 i >elements, but the • html () method
returns only the contents of the first one. This is then appended to the
end of the selection, in this case after each existing <1 i> element.
```

**JAVASCRIPT**

```
var $1istltemText = $('1i ').text();
${'li ').append('<i>' + $1istltemText + '</ i>
```

###  jQuery Cheat Sheet
![ jQuery Cheat Sheet](https://blog.templatetoaster.com/wp-content/uploads/2018/02/OverAPI-jQuery-Cheat-Sheet.jpg)

### LOADING JQUERY FROM A CDN
```
<script src=" //ajax .googl eapi s . com/ ajax/l i bs/ jquery / 1.10. 2/ jquery .min. js ">
</ script>
<script>
window .jQuery 11 document. write (' <script src=" j s/j query- 1.10. 2 .j s 11><\jscri pt> ' )
</script> 
```
