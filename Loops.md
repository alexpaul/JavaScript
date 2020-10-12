# Loops 

## `while` loop

```javascript 
const raceDistances = ['Sprint', 'Olympic', 'Half-IRONMAN', 'Full IRONMAN']; 
```

```javascript 
let index = 0; 
while (index < raceDistances.length) {
  const distance = raceDistances[index]; 
  console.log(`Race distance is ${distance}`); 
  index++; 
}
```


## `for` loop

```javascript 
const raceDistances = ['Sprint', 'Olympic', 'Half-IRONMAN', 'Full IRONMAN']; 
```

```javascript
for(let index = 0; index < raceDistances.length; index++) {
  console.log(raceDistances[index]); 
}
```


## `for...of` loop

```javascript 
const raceDistances = ['Sprint', 'Olympic', 'Half-IRONMAN', 'Full IRONMAN']; 
```

```javascript 
for (let distance of raceDistances) {
  console.log(distance); 
}
```
