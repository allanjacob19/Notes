# Express JS -Middleware

```js
var http=require("http");

var express=require("express");

var app=express();

app.use('/',(req,res,next)=>{

    console.log("This always runs");

    next();
})
app.use('/add-product',(req,res,next)=>{

    console.log("In the Middleware");

    res.send('<h1>In add-product Page</h1>');

    next(); //Allows the request to continue to next middleware in line

});

app.use('/',(req,res,next)=>{

    console.log("In the Next Middleware");

    res.send('<h1>Hello from Express</h1>')// send allows the text to automatically convert to html format without the use of any header

});

const server=http.createServer(app);

server.listen(3000);
```
``
## Output

 In the Middleware
 In the next Middleware