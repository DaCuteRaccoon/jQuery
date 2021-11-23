# jQuery
You can import jQuery within a JavaScript file!<br/>
Just put the following in your code:<br/>
```js
function import_jQuery() {
  var script = document.createElement('script');
  script.src = 'https://code.jquery.com/jquery-3.4.1.min.js';
  script.type = 'text/javascript';
  document.getElementsByTagName('head')[0].appendChild(script);
 }
```
Now, all you have to do is call `import_jQuery()`, and jQuery will now be imported!<br/>
The reason I put this into a function is because you can check if jQuery is already imported.<br/>
Let's create a variable, called `JQUERY`.<br/>
I made this in ALL CAPS because if jQuery is loaded, there will be a function with the same name.<br/>
```js
JQUERY = null;
```
Don't do `var JQUERY = null;` or `let JQUERY = null;` because this won't allow us to `delete(JQUERY)` afterwards.<br/>
Now that we have that in our code, let's check if jQuery is imported.<br/>
```js
if (window.jQuery) {
  // jQuery is loaded  
  JQUERY = true
} else {
  // jQuery is not loaded
  JQUERY = false
}
```
Now, it knows if jQuery is already imported or not. But it didn't call `import_jQuery` yet.
```js
if (JQUERY == true) {
  console.log('jQuery is already loaded.')
  delete(JQUERY)
} else {
  console.log('Loaded jQuery.')
  import_jQuery()
}
```
That's all! You can download the code [here](script.js), and the userscript [here](data:text;base64,U29ycnkhIEkgaGF2ZW4ndCBtYWRlIGEgdXNlcnNjcmlwdCB5ZXQuIENvbWluZyBzb29uIQ==).
