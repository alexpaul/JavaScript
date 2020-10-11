# Date 

## Create today's Date 

```javascript 
const now = new Date(); 
console.log(now); // 2020-10-11T11:26:42.835Z - time is offset from UTC 
```

## Creating a custom Date 

```javascript 
const swiftLaunch = new Date(2014, 8, 8); // year, month, day
console.log(swiftLaunch); // 2014-09-08T00:00:00.000Z
```

## Using `setMonth()` and `setDate()`

```javascript 
const commencementDate = new Date(); 
commencementDate.setMonth(9); // months start from 0 
commencementDate.setDate(12); 

console.log(commencementDate); // 2020-10-12T11:36:04.975Z
```

## Using `getDay()`

```javascript 
console.log(`Commencement in on a ${commencementDate.getDay()}`); // 1 is Monday
```

## Challenges 

#### Challenge 1 

Write a JavaScript function to get the number of days in a month.

Test Data :
```javascript 
console.log(getDaysInMonth(1, 2012));
console.log(getDaysInMonth(2, 2012));
console.log(getDaysInMonth(9, 2012));
console.log(getDaysInMonth(12, 2012));
```

Output :  
31  
29  
30  
31  

<details> 
  <summary>Solution</summary> 

```javascipt 
function getDaysInMonth(month, year) {
  let date = new Date(year, month, 0); // last day is represented by 0
  return date.getDate(); 
}

console.log(getDaysInMonth(1, 2012)); // 31
console.log(getDaysInMonth(2, 2012)); // 29
console.log(getDaysInMonth(9, 2012)); // 30
console.log(getDaysInMonth(12, 2012));// 31
console.log(getDaysInMonth(10, 2020)); // 31
```
  
</details> 

## Resouces 

1. [MDN - Date](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Date)
1. [JavaScript Date - Exercises, Practice, Solution
](https://www.w3resource.com/javascript-exercises/javascript-date-exercises.php)

