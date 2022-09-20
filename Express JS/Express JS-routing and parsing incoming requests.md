# Routing and Parsing Incoming Requests

```js
var http=require("http");

var bodyParser=require("body-parser");

var express=require("express");

var app=express();

app.use(bodyParser.urlencoded({extended:false})); //Used for printing the body contents in "console.log(req.body);"

app.use('/',(req,res,next)=>{

    console.log("This always runs");

    next();

})

app.use('/add-product',(req,res,next)=>{

    console.log("In the Middleware");

    res.send('<form action="/product" method="POST"><input type="text" name="title"><button type="submit">Add Product</button></form>');

    next(); //Allows the request to continue to next middleware in line

});

app.use('/product',(req,res,next)=>{

    console.log("In the Body");

    console.log(req.body);

    res.redirect("/");

})

app.use('/',(req,res,next)=>{

    console.log("In the Next Middleware");

    res.send('<h1>Hello from Express</h1>')// send allows the text to automatically convert to html format without the use of any header

});

const server=http.createServer(app); 

server.listen(3000);
```