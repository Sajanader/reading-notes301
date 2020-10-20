#  Flexbox and Templating
### Javascript Templating
Javascript templating is a fast and efficient technique to render client-side view templates with Javascript by using a JSON data source. The template is HTML markup, with added templating tags that will either insert variables or run programming logic.


![image](https://miro.medium.com/max/875/1*LbqYj87xlazySm6wE0Q2lA.png)

* Mustache-Express
To install:
With Yarn:
```$ yarn add mustache-express```
or with NPM:
```$ npm install mustache --save``
Create a views folder and add some html view templates (e.g. hello.html):
Then in the router configuration, use res.render(TEMPLATE_NAME, JSON_DATA). Example:
```res.render('hello', {"name": "Sherlynn"})```
The second parameter would be the JSON data itself. We can also pass in a variable representing the data, for example:
```var nameObject = {"name": "Sherlynn"}``
```res.render('hello', nameObject)```
the final  output
![image](https://miro.medium.com/max/875/1*YaJ1vtsuwRMhfi8parlHOA.png)


## flexbox
This defines a flex container; inline or block depending on the given value. It enables a flex context for all its direct children.

```
.container {
  display: flex; /* or inline-flex */
}
```

* flex direction
This establishes the main-axis, thus defining the direction flex items are placed in the flex container. Flexbox is (aside from optional wrapping) a single-direction layout concept. Think of flex items as primarily laying out either in horizontal rows or vertical columns.

```
.container {
  flex-direction: row | row-reverse | column | column-reverse;
}
```

* flex wrap
By default, flex items will all try to fit onto one line. You can change that and allow the items to wrap as needed with this property.
```
.container {
  flex-wrap: nowrap | wrap | wrap-reverse;
}
```
* flex-flow
This is a shorthand for the flex-direction and flex-wrap properties, which together define the flex container’s main and cross axes. The default value is row nowrap.
```
.container {
  flex-flow: column wrap;
}
```