# app.js

```js
const express = require('express');

const bodyParser = require('body-parser');

const app = express();
[[Express JS-Middleware]]
const adminRoutes = require('./routes/admin'); //taking all the routes from admin from where we imported and putting here

const shopRoutes = require('./routes/shop');

app.use(bodyParser.urlencoded({extended: false}));

app.use(adminRoutes);//Importing all the routes in admin.js to here

app.use(shopRoutes);

app.listen(3000);
```