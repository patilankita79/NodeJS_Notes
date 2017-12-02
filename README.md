# NodeJS_Notes
 Node.js is a run-time environment for executing server-side JavaScript code.

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Node JS Fundamentals

<hr>

### What is Node.js?
<ol>
  <li>Node.js is a Javascript runtime that uses Chrome's V8 engine.</li>
  <li>V8 is an Open source Javascript engine written in C++ that take Javascript code and compiles into machine code. This engine is used inside of Node js and Chrome browser</li>
</ol>

### What you can do with Node.js applications?
<ol>
<li>Manipulate file system -> creating and removing folders</li>
<li>Create databases</li>
<li>Create web server</li>
</ol>

### Why Node.js? 
```
Asynchronous, event-based, non-blocking
```
<ol>
  <li>Node.js uses event driven, non-blocking I/O model</li>
  <li>Node.js is single threaded, means the application runs in a single thread</li>
</ol>
 
### Node JS Package Ecosystem - Node.js Package Manager(NPM)
<ol>
<li>NPM is the package manager for Javascript</li>
<li>NPM allows packages and modules for node</li>
<li>All 3rd party libraries or modules, we can get from NPM as per the requirement of our application. </li>
<li>Every 3rd party library present in NPM uses non-blocking I/O model</li>
</ol>

### NodeJS built-in modules 

Node modules are similar to JS libraries <br>
Complete list can be found <a href="https://nodejs.org/api/"> here.</a>
Few built-in modules are mentioned in the following table.<br>

<table>
<th>Module</th>
<th>Description</th>
  <tr>
  <td>http</td>
  <td>To make node.js to act as HTTP Server</td>
  </tr>
  <tr>
  <td>https</td>
  <td>To make node.js to act as HTTPS server</td>
  </tr>
  <tr>
  <td>fs</td>
  <td>To handle the file system</td>
  </tr>
  <tr>
  <td>path</td>
  <td>To handle file path</td>
  </tr>
  <tr>
  <td>events</td>
  <td>To handle events</td>
  </tr>
  
</table>

### Using modules

<p>Modules(built-in Node modules or 3rd party library or your own files) can be used in program using <b>require</b> function (Anology:<i> Can be thought as <b>import</b> statement in Java</i>)</p>


### package.json
<ul>
<li>package.json is the main manifest file which should be present in the root of application.</li>
<li>It tells NPM how your package is structured and what to do to install it.</li>
</ul> 
<p>package.json can be set either manually or using command,</p>

```
npm init
```


# Working with JSON inside node.js

### Write a JSON file

```
// Load file system module
const fs = require('fs');

var personObject = {
  firstName: 'Ankita',
  lastName: 'Patil'
}

//Converting object to string
var personString = JSON.stringify(personObject)

// Following command creates a file (if not present) and writes personString into demo.json
fs.writeFileSync('demo.json', personString);

```

### Reading the contents of JSON file

```
var personContent = fs.readFileSync('demo.json');

// Converting string back to object
var person = JSON.parse(personContent)

// Acessing object value
console.log(person.firstName)
```

<hr>

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Asynchronous Node.js

<hr>
In simple terms, <br>
Asynchronous is when you don't halt your program, for example when you are making requests to the internet, which is inherently asynchronous. app will continue to run while it waits for someting else to happen <br>If you were to do a sychronous call to some API on the internet then the app would freeze up until the response came back.

### Callback function

It is defined as a function that gets passed as an argument to another function, and is executed after some event.

```
setTimeout(() => {
console.log('Inside callback function');
}, 2000);
```
<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Promises

<hr>

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Web server using Node.JS

<hr>

Web server can be created with the help of a library called <a href="http://expressjs.com/">express</a>.


### A simple web server using express

```
//load express
const express = require('express');

var app = express();

/*
setting http route handlers
*/

//register handler using app.get
app.get('/', (req, res) => {

  // if the user makes a request, he will get response for the http request
  //response for the http request
  // res.send('<h1>Hello Express</h1>');

  res.send({
    name: 'Ankita'
  })
});

app.get('/about', (req, res) => {
  res.send('<h1>About page</h1>')
});

// /bad -> send back json with errorMessage
app.get('/bad', (req, res) => {
  res.send({
    errorMessage:'Unable to handle request'
  });
});

// bind application to port on a machine
app.listen(3000);
```

<hr>

# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Testing NodeJs applications

<hr>

1. Using <a href="https://mochajs.org/">Mocha</a> framework

<blockquote>A test case is function that runs some code. If things go well, test case is considered to have passed otherwise test case is considered to have failed</blockquote>

```
npm install mocha --save-dev
```

flag save-dev will save mocha for development purpose only. The dependecy will be installed only locally and Hence, mocha will not run in  app or deployed app. It will be saved under "devDependencies" in package.json
<br>
<ul>
 <li>In mocha, new test is created using <b>it</b> (It is a function provided by Mocha framework)</li>
</ul>
