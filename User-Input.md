# Reading STDIN user input 

## Using `prompt()`
Reading in input from the user can be done using `prompt()` .

> prompt() will only work in browsers, not in IDE's such as VSCode. 

```javascript 
const iOSMessage = 'Looks like you develop for Apple devices.'; 
const webMessage = 'Hello, full stack dev.'; 

const input = Number(prompt('Please enter 1 for Swift or 2 for Web?'));

if (input === 1) {
  console.log(iOSMessage);
} else {
  console.log(webMessage); 
}
```

![prompt console](https://user-images.githubusercontent.com/1819208/96650431-e6521980-1300-11eb-937d-fa63891e3bbf.png)

Try it in [repl.it](https://repl.it)

## `readline` package 

```javascript 
var readline = require("readline");

const r1 = readline.createInterface({
    input: process.stdin, 
    output: process.stdout
}); 

r1.question('Do you want to hit or pass ?', (answer) => {
    console.log(`You entered ${answer}`); 

    r1.close(); 
}); 
```

#### Looping with `readline`

In order to create a looping structure e.g creating a Text Adventure game or a BlackJack game using `readline` you must use a recursive function as a `while` or `do...while` won't execute continuosuly using `readline`. 

```javascript 
const gamePlay = function() {
  r1.question('Enter yes or no?', (answer) => {
    console.log(`You answered ${answer}`); 
    if (answer !== 'yes') {
      return r1.close(); 
    }
    gamePlay(); 
  }); 
}; 

gamePlay(); 
```

[Stackoverflow - How to readline infinitely in node](https://stackoverflow.com/questions/24464404/how-to-readline-infinitely-in-node-js)


## Resource 

1. [MDN - Window.prompt()](https://developer.mozilla.org/en-US/docs/Web/API/Window/prompt)
