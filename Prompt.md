# Prompt 

Getting input from the user can be done using `prompt()`

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
