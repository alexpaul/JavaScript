# Express

## Serving static pages 

Create a folder named `www` in the project's root directory and place static e.g `.html` pages there. 

Create a file called `server.js` and add the following code. 

```javascript 
const express = require('express');
const app = express();

app.use(express.static(__dirname + '/www'));

app.listen('3000');
console.log('working on 3000');
```

Launch your web server `node server.js`

