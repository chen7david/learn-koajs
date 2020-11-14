# Adding A Router

### Routes
So far our Koa application responds "Not Found" to any request that is send to it. Adding a router will help us respond to specific requests. The code below will show you how to add a router to your koa application. 

```js
// src/routes/example 

const Router = require('koa-router')
const router = new Router()
const controller = require('./controllers/ExampleController.js')

/* ROUTE DEFINITIONS */

// RUNS paramLoader function first on each request that includes the :id param in the url path
router.param('id', controller.paramLoader)

// HOME ROUTE
router.get('/', controller.home)

// QUERY PARAM
router.get('/animals', controller.queryParam)

// PATH PARAM
router.get('/animal/:id', controller.pathParam)

module.exports = router
```

### Controllers
Controllers provide all the logic and functionality of your app. They are responsible for returing a result to the client.

```js
// src/controllers/ExampleController.js

module.exports = {

    home: async (ctx, next) => {
        ctx.body = 'Welcome to our Home Page'
    },

    paramLoader: async (id, ctx, next) => {
        console.log({id})
        return next()
    },

    queryParams: async (ctx, next) => {
        const queryParams = ctx.request.query
        ctx.body = {
            msg: 'Query Params are below.',
            queryParams
        }
    },

    pathParams: async (ctx, next) => {
        const pathParams = ctx.params
        ctx.body = {
            msg: 'Path Params are below.',
            pathParams
        }
    },

    bodyParams: async (ctx, next) => {
        const bodyParams = ctx.request.body
        ctx.body = {
            msg: 'Path Params are below.',
            bodyParams
        }
    },
}
```