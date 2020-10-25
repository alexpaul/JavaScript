# Node and Packages

Node is a JavaScript runtime that allows building of server-side and client-side applications. 

## What is a package?  

Node is shipped with a package manager, called `npm`, Node package manager, similar to Cocoapod or Swift Package manager that allows for the installation of third party dependencies. 

A package in Node can be used to accomplish the following: 

* Libraries
* Tools 
* Shared Components 
* Your app

## [NPM](https://www.npmjs.com/) 

A registry to search for packages. 

## package.json 

The `package.json` file is created when the following command is ran in terminal: 

```npm init```

The `package.json` file contains the following: 

* Metadata - your project's name, version, descrption, author, repository, license, etc 
* Dependencies - the list of packages used by your project 
* Scripts - commands to automate development tasks 

## Installing a package 

Download and add package and dependencies to be included in production.

```npm install <package-name>```

Download and add package to dev dependencies that will only be used for development and not shipped with the app. 

```npm install --save-dev <package-name>```

## An example usage of adding dependencies to a Node application 

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
