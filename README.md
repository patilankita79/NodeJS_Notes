# NodeJS_Notes
 Node.js is a run-time environment for executing server-side JavaScript code.

<hr>
# ![#f03c15](https://placehold.it/15/f03c15/000000?text=+) Node JS Fundamentals
<hr>

## What is Node.js?
<ol>
  <li>Node.js is a Javascript runtime that uses Chrome's V8 engine.</li>
  <li>V8 is an Open source Javascript engine written in C++ that take Javascript code and compiles into machine code. This engine is used inside of Node js and Chrome browser</li>
</ol>

## What you can do with Node.js applications?
<ol>
<li>Manipulate file system -> creating and removing folders</li>
<li>Create databases</li>
<li>Create web server</li>
</ol>

## Why Node.js?
<ol>
  <li>Node.js uses event driven, non-blocking I/O model</li>
  <li>Node.js is single threaded, means the application runs in a single thread</li>
</ol>
 
## Node JS Package Ecosystem - Node.js Package Manager(NPM)
<ol>
<li>NPM is the package manager for Javascript</li>
<li>NPM allows packages and modules for node</li>
<li>All 3rd party libraries or modules, we can get from NPM as per the requirement of our application. </li>
<li>Every 3rd party library present in NPM uses non-blocking I/O model</li>
</ol>
 
 <hr>

## NodeJS built-in modules 

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


<hr>

# Node JS fundamentals

<ol>
<li>Modules(built-in Node modules or 3rd party library or your own files) can be used in program using <b>require</b> function (Anology:<i> Can be thought as <b>import</b> statement in Java</i>)</li>
<li>package.json is the main manifest file which should be present in the root of application. Package.json tells NPM how your package is structured and what to do to install it. package.json can be set either manually or using command => npm init</li>
</ol>

<hr>

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
