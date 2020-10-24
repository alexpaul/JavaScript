# Packages 

## What is a package?  

* Libraries
* Tools 
* Shared Components 
* Your app

## NPM 

A registry to search packages. 

## package.json 

Create a `package.json` file 

```npm init```

* Metadata - your project's name, version, descrption, author, repository, license, etc 
* Dependencies - the list of packages used by your project 
* Scripts - commands to automate development tasks 

## Install a package 

Download and add package and dependencies 

```npm install <package-name>```

Download and add package to dev dependencies

```npm inall --save-dev <package-name>```

## Usage 

#### 1. Install `readline` package 

```npm install readline```

#### 2. `require` the package in your JavaScript file 

```javascript 
var readline = require("readline");
```

#### 3. Using the installed package 

```javascript 
const r1 = readline.createInterface({
    input: process.stdin, 
    output: process.stdout
}); 
```
