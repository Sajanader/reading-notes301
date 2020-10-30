SuperAgent
SuperAgent is light-weight progressive ajax API crafted for flexibility, readability, and a low learning curve after being frustrated with many of the existing request APIs. It also works with Node.js!
```
 request
   .post('/api/pet')
   .send({ name: 'Manny', species: 'cat' })
   .set('X-API-Key', 'foobar')
   .set('Accept', 'application/json')
   .then(res => {
      alert('yay got ' + JSON.stringify(res.body));
   });
   ```
Test documentation
The following test documentation was generated with Mocha's "doc" reporter, and directly reflects the test suite. This provides an additional source of documentation.

Request basics
A request can be initiated by invoking the appropriate method on the request object, then calling .then() (or .end() or await) to send the request. For example a simple GET request:
```
 request
   .get('/search')
   .then(res => {
      // res.body, res.headers, res.status
   })
   .catch(err => {
      // err.message, err.response
   });
   ```
HTTP method may also be passed as a string:

request('GET', '/search').then(success, failure);
Old-style callbacks are also supported, but not recommended. Instead of .then() you can call .end():

request('GET', '/search').end(function(err, res){
  if (res.ok) {}
});
Absolute URLs can be used. In web browsers absolute URLs work only if the server implements CORS.
```
 request
   .get('https://example.com/search')
   .then(res => {

   });
   ```
The Node client supports making requests to Unix Domain Sockets:
```
// pattern: https?+unix://SOCKET_PATH/REQUEST_PATH
//          Use `%2F` as `/` in SOCKET_PATH
try {
  const res = await request
    .get('http+unix://%2Fabsolute%2Fpath%2Fto%2Funix.sock/search');
  // res.body, res.headers, res.status
} catch(err) {
  // err.message, err.response
}
```
DELETE, HEAD, PATCH, POST, and PUT requests can also be used, simply change the method name:
```
request
  .head('/favicon.ico')
  .then(res => {

  });
  ```
DELETE can be also called as .del() for compatibility with old IE where delete is a reserved word.

The HTTP method defaults to GET, so if you wish, the following is valid:
```
 request('/search', (err, res) => {

 });
Setting header fields
Setting header fields is simple, invoke .set() with a field name and value:

 request
   .get('/search')
   .set('API-Key', 'foobar')
   .set('Accept', 'application/json')
   .then(callback);
   ```
You may also pass an object to set several fields in a single call:
```
 request
   .get('/search')
   .set({ 'API-Key': 'foobar', Accept: 'application/json' })
   .then(callback);
   ```
GET requests
The .query() method accepts objects, which when used with the GET method will form a query-string. The following 
```
will produce the path /search?query=Manny&range=1..5&order=desc.

 request
   .get('/search')
   .query({ query: 'Manny' })
   .query({ range: '1..5' })
   .query({ order: 'desc' })
   .then(res => {

   });
   ```
Or as a single object:
```
request
  .get('/search')
  .query({ query: 'Manny', range: '1..5', order: 'desc' })
  .then(res => {

  });
  ```
The .query() method accepts strings as well:
```
  request
    .get('/querystring')
    .query('search=Manny&range=1..5')
    .then(res => {

    });
    ```
Or joined:
```
  request
    .get('/querystring')
    .query('search=Manny')
    .query('range=1..5')
    .then(res => {

    });
    ```
HEAD requests
You can also use the .query() method for HEAD requests. The following will produce the path /users?email=joe@smith.com.
```
  request
    .head('/users')
    .query({ email: 'joe@smith.com' })
    .then(res => {

    });
    ```
POST / PUT requests
A typical JSON POST request might look a little like the following, where we set the Content-Type header field appropriately, and "write" some data, in this case just a JSON string.
```
  request.post('/user')
    .set('Content-Type', 'application/json')
    .send('{"name":"tj","pet":"tobi"}')
    .then(callback)
    .catch(errorCallback)
    ```
Since JSON is undoubtedly the most common, it's the default! The following example is equivalent to the previous.
```
  request.post('/user')
    .send({ name: 'tj', pet: 'tobi' })
    .then(callback, errorCallback)
    ```
Or using multiple .send() calls:
```
  request.post('/user')
    .send({ name: 'tj' })
    .send({ pet: 'tobi' })
    .then(callback, errorCallback)
    ```