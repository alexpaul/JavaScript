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


## `for` loop

```javascript 
const raceDistances = ['Sprint', 'Olympic', 'Half-IRONMAN', 'Full IRONMAN']; 
```

```javascript
for(let index = 0; index < raceDistances.length; index++) {
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
