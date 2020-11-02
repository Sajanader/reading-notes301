# read-11.md
# <%= EJS %>
## What is EJS?
What is the "E" for? "Embedded?" Could be. How about "Effective," "Elegant," or just "Easy"? EJS is a simple templating language that lets you generate HTML markup with plain JavaScript. No religiousness about how to organize things. No reinvention of iteration and control-flow. It's just plain JavaScript.

## features:
* Use plain JavaScript
* Speedy execution
* Fast development time
* Simple syntax
* Active development
* Easy debugging

### Install
It's easy to install EJS with NPM.

$ npm install ejs
Use
Pass EJS a template string and some data. BOOM, you've got some HTML.
```
let ejs = require('ejs');
let people = ['geddy', 'neil', 'alex'];
let html = ejs.render('<%= people.join(", "); %>', {people: people});
```
### CLI
Feed it a template file and a data file, and specify an output file.

ejs ./template_file.ejs -f data_file.json -o ./output.html
Browser support
Download a browser build from the latest release, and use it in a script tag.
```
<script src="ejs.js"></script>
<script>
  let people = ['geddy', 'neil', 'alex'];
  let html = ejs.render('<%= people.join(", "); %>', {people: people});
</script>
```
### Docs
Example
```
<% if (user) { %>
  <h2><%= user.name %></h2>
<% } %>
```
### Usage
let template = ejs.compile(str, options);
template(data);
```
// => Rendered HTML string

ejs.render(str, data, options);
// => Rendered HTML string

ejs.renderFile(filename, data, options, function(err, str){
    // str => Rendered HTML string
});
```