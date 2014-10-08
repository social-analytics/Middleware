#Middleware Config guide
*How to set middleware in Node.js*


## Table of Contents
  1. [Middleware Config](#middleware config)
  2. [Universal Middleware](#universal middleware)
  3. [Customed Middleware](#customed middleware)

## Middleware Config
  + Set middleware for all routes or some specific routes
  
  ###middleware for all route
    ```javascript
    var express = require('express')
    var middleware = require(Middleware)
    
    var app = express()
    
    //all routes will pass middleware
    app.use(middleware)
    ```
    
  ###middleware for some specific routes
    ```javascript
    var express = require('express')
    var middleware = require(Middleware)    
    
    var app = express()
    
    //only routes like /name/xxx will pass the middleware
    app.use('/name', middleware)
    ```
## Universal Middleware
  + Express 4 has remove many middlewares which are auto included in express 3. Below are 3 kinds of middleware that we will use.

  ###body-parser
    ```javascript
    var express = require('express')
    var bodyParser = require('body-parser')

    var app = express()

    // parse application/x-www-form-urlencoded
    app.use(bodyParser.urlencoded({ extended: false }))

    // parse application/json
    app.use(bodyParser.json())
    ```
    [More Info](https://github.com/expressjs/body-parser)
  
  ###express-session
    ```javascript
    var express = require('express')
    var session = require('express-session')

    var app = express()

    app.use(session({secret: 'keyboard cat'}))
    ```
    [More Info](https://github.com/expressjs/session)
  
  ###cookie-parser
    ```javascript
    var express = require('express')
    var cookieParser = require('cookie-parser')

    var app = express()
    app.use(cookieParser())
    ```
    [More Info](https://github.com/expressjs/cookie-parser)

## Customed Middleware


