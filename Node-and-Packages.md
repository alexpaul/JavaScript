# Node and Packages

[Node](https://nodejs.org/en/) is a **JavaScript runtime** that allows building of server-side and client-side applications. 

## 1. What is a package?  

Node is shipped with a package manager, called `npm`, Node package manager, similar to Cocoapod or Swift Package manager allows for the installation of third party dependencies. 

A package in Node can be used to add the following: 

* Libraries
* Tools 
* Shared Components 
* Your app

## 2. [npmjs.com](https://www.npmjs.com/) 

An online egistry to search for node packages. 

## 3. Initialize `npm` in an application and create a `package.json` file 

The `package.json` file is created when the following command is ran in terminal: 

```npm init```

The `package.json` file contains the following: 

* Metadata - your project's name, version, descrption, author, repository, license, etc 
* Dependencies - the list of packages used by your project 
* Scripts - commands to automate development tasks e.g `npm start` will run the application server

Example of a `package.json` file 

```json 
{
  "name": "demo-web-server",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "Alex Paul",
  "license": "ISC"
}
```

To bypass initialization questions 

`npm init -y`

## 4. Installing a package 

Download and add package and dependencies to be included in production.

```npm install <package-name>```

Download and add package to dev dependencies that will only be used for development and not shipped with the app. 

```npm install --save-dev <package-name>```

## A few Node package installations and use cases

## 5. `readline` Package 

#### 1. Install `readline` package 

The `readline` package allows for reading in user input from the command line. 

```npm install readline```

#### 2. `require` the package in your JavaScript file 

```javascript 
const readline = require("readline");
```

#### 3. Using the installed package 

```javascript 
const r1 = readline.createInterface({
    input: process.stdin, 
    output: process.stdout
}); 

r1.question('Please enter your name?', (name) => {
    console.log(`Hello, ${answer}, welcome to Node development.`); 

    r1.close(); // need to close the readline connection to return to the application's regular execution
}); 
```

## 6.`prettier` Package 

Prettier is used to format JavaScript code. 

Install `prettier`

`npm install --save-dev prettier`

Edit the `package.json` scripts property to allow for quick running of `format`

```javascript 
"scripts": {
  "format": "prettier --write *.js"
}
```

Usage 

```npm run format```


## 7. `nodemon` Package

Nodemon is used to automatically watch for changed files and re-run the node server. 

Install `nodemon`

```javascript
npm install -g nodemon // using the -g flag enables the package to be available globally throughout applications
```

Usage, now instead of using `node <script name>` to run a script we use: 

```nodemon <script name>```

To restart a running application 

```rs```

## 8. `express` Package

`express` is a Node package that allows us to create web servers to host APIs that allow for http request, reponses and supports HTTP methods e.g GET and POST.

Install `express` 

`npm install express` 

An example of web server JavaScript code that will listen on a specific port and render "Hello, world" if the API address is visited. 

Save the following code in a file called `index.js` 

```javascript 
const express = require('express'); 
const app = express(); 
const port = 3000; 

app.get('/', (request, response) => {
    response.send(`Hello World!`); 
}); 

app.listen(port, () => {
    console.log(`Example app listening at http://localhost:${port}`); 
}); 
```

To run the `express` web server 

```node index.js```

Edit the `package.json` to include a run script

```javascript 
"scripts": {
  "start": "node index.js"
}
```

Using the run script 

```npm start```

## 9. `dotenv` Package

`dotenv` allows for environment variables configuration, such as managing API keys and credentials. 

Install `dotenv`

```npm install dotenv```


Edit the web server JavaScript file 

```javascript 
require('dotenv').config(); 

const express = require('express'); 
const app = express(); 
const port = process.env.PORT; 

console.log(port); // 5000
```

Create a `.env` file 

```
PORT=5000
```

Re-run the web server and all should still work as before, only this time the the port number is not exposed in the JavaScript code. 

> Don't forget to add your `env` file to the `.gitignore` 

[Read more about the dotenv Package](https://www.npmjs.com/package/dotenv)

