# Data Structures 

## Stack 

```javascript 
class Stack {
  constructor() {
    this.elements = []; 
  }

  peek() {
    return this.elements[this.elements.length - 1]; 
  }

  isEmpty() {
    return this.elements.length === 0; 
  }

  push(element) {
    this.elements.push(element); 
  }

  pop() {
    if (this.elements.length === 0) {
      return 'empty'
    }
    return this.elements.pop(); 
  }
}

let stack = new Stack(); 

console.log(stack.isEmpty()); // true 

stack.push('Alex');
stack.push(6.3);

console.log(stack.peek()); // 6.3
```
