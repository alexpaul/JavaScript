# Loops 

## `while` loop

```javascript 
const raceDistances = ['Sprint', 'Olympic', 'Half-IRONMAN', 'Full IRONMAN']; 
```

```javascript 
let index = 0; 
while (index < raceDistances.length) {
  const distance = raceDistances[index]; 
  console.log(distance); 
  index++; 
}

/*
Sprint
Olympic
Half-IRONMAN
Full IRONMAN
*/
```


## C-style `for` loop

```javascript 
const raceDistances = ['Sprint', 'Olympic', 'Half-IRONMAN', 'Full IRONMAN']; 
```

```javascript
for (let index = 0; index < raceDistances.length; index++) {
  console.log(raceDistances[index]); 
}

/*
Sprint
Olympic
Half-IRONMAN
Full IRONMAN
*/
```


## `for...of` loop

This for loop gives you access to each element in the collection as you're iterating. 

```javascript 
const raceDistances = ['Sprint', 'Olympic', 'Half-IRONMAN', 'Full IRONMAN']; 
```

```javascript 
for (const distance of raceDistances) {
  console.log(distance); 
}

/*
Sprint
Olympic
Half-IRONMAN
Full IRONMAN
*/
```

## `for...in` loop 

This for loop gives you access to the current index as you're looping through a collection. 

```javascript 
const arr = ['Bob', 'Sally', 'Tim']; 
for (const index in arr) {
  console.log(index); // 0, 1, 2
}
```

## Challenges 

#### Challenge 1 

Write a JavaScript for loop that will iterate from 0 to 15. For each iteration, it will check if the current number is odd or even, and display a message to the console.

<details>
  <summary>Solution</summary>
  
```javascript 
for (let num = 0; num < 16; num++) {
  if (num % 2 === 0) {
    console.log(`${num} is even.`); 
  } else {
    console.log(`${num} is odd.`); 
  }
}

/*
0 is even.
1 is odd.
2 is even.
3 is odd.
4 is even.
5 is odd.
6 is even.
7 is odd.
8 is even.
9 is odd.
10 is even.
11 is odd.
12 is even.
13 is odd.
14 is even.
15 is odd.
*/
```

</details> 

***

#### Challenge 2

Write a JavaScript program which iterates the integers from 1 to 100. But for multiples of three print "Fizz" instead of the number and for the multiples of five print "Buzz". For numbers which are multiples of both three and five print "FizzBuzz".

<details>
  <summary>Solution</summary>
  
```javascript 
for (let num = 1; num < 101; num++) {
  if (num % 3 === 0 && num % 5 === 0) {
    console.log('FizzBuzz'); 
  }
  else if (num % 3 === 0) {
    console.log('Fizz'); 
  }
  else if (num % 5 === 0) {
    console.log('Buzz'); 
  } else {
    console.log(num); 
  }
}

/*
1
2
Fizz
4
Buzz
Fizz
7
8
Fizz
Buzz
11
Fizz
13
14
FizzBuzz
16
17
*/
```

</details> 

***

#### Challenge 3

Write a JavaScript program to construct the following pattern, using a nested for loop.

```javascript 
*  
* *  
* * *  
* * * *  
* * * * *  
```

<details>
  <summary>Solution</summary>
  
```javascript 
for (let num = 1; num < 6; num++) {
  let str = ''; 
  for (let asterik = 0; asterik < num; asterik++) {
    str += '* ';
  }
  console.log(str); 
}

/*
* 
* * 
* * * 
* * * * 
* * * * * 
*/
```

</details> 

***

#### Challenge 4

Create a loop that runs through each item in the fruits array.

```javascript
const fruits = ["Apple", "Banana", "Orange"];
```

<details>
  <summary>Solution</summary>
  
```javascript 
const fruits = ["Apple", "Banana", "Orange"];

for (const fruit of fruits) {
  console.log(fruit); 
}

/*
Apple
Banana
Orange
*/
```

</details> 

***

#### Challenge 5

Multiplication Tables

Write a for loop that will iterate from 0 to 10. For each iteration of the for loop, it will multiply the number by 9 and log the result (e.g. "2 * 9 = 18").

Bonus: Use a nested for loop to show the tables for every multiplier from 1 to 10 (100 results total).

<details>
  <summary>Solution</summary>
  
```javascript 
for (let num = 1; num < 11; num++) {
  console.log(`========= ${num} Times Table =========`); 
  for (let multiplier = 1; multiplier < 11; multiplier++) {
    console.log(`${num} * ${multiplier} = ${num * multiplier}`); 
  }
}

/*
========= 1 Times Table =========
1 * 1 = 1
1 * 2 = 2
1 * 3 = 3
1 * 4 = 4
1 * 5 = 5
1 * 6 = 6
1 * 7 = 7
1 * 8 = 8
1 * 9 = 9
1 * 10 = 10
========= 2 Times Table =========
2 * 1 = 2
2 * 2 = 4
2 * 3 = 6
2 * 4 = 8
2 * 5 = 10
2 * 6 = 12
2 * 7 = 14
2 * 8 = 16
2 * 9 = 18
2 * 10 = 20
.
.
.
*/
```

</details> 

***
