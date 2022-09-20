# user.js file

```js
const express = require('express');

const router = express.Router();

router.get('/', (req, res, next) => {

res.send('<h1>Hello from Express!</h1>'); //send allows the text to automatically convert to html format without the use of any header
});

module.exports = router;
```
