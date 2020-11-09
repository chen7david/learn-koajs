# Getting Started

#### Lesson Objectives
In this lesson, we will learn how to set up a minimalistic webserver. 
- We will first learn how to setup a node project 
- then we will download the koa package from nmp (node package manager)
- then finally we will use the require function to bring in the koa class, instantiate it and have it listen to a port of our choice.

#### Steps
1. Create a new folder <code>command</code> + <code>shift</code> + n 
2. Open the folder wiht VsCode
3. In the top menu-bar of VsCode select view->Terminal to open the conse
4. in the console type: <code>$ npm init -y</code> to create a package.json file that will help you manage your project. 
4. install koa by running: <code>$ npm i koa</code> 
5. create a new file and name it <code>index.js</code> 
6. create a server by writing the followign code in your <code>index.js</code> page.

```js
const Koa = require('koa')
const app = new Koa()
const port = 3000

/* add code here ... */

app.listen(3000)
```

7. create an sync function with <code>ctx</code> as its parameter.
```js
const someFunction = async (ctx) => {

}
```
8. in your async function set the body of the ctx prameter to a string like shown below.
```js
    ctx.body = 'hello from your server'
```
If you follwed all the steps so far your <code>index.js</code> file should look this:

```js
const Koa = require('koa')
const app = new Koa()
const port = 3000

const someFunction = async (ctx) => {
    body.ctx = 'hello from your server'
}
`
app.listen(3000)
```
9. The function we just created is considered middleware in koa, lets add it to koa so we can start using our server. We add middleware to koa by calling the <code>use()</code> method on a koa instance.
```js
    app.use(someFunction)
```