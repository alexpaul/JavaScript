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
