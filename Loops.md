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
