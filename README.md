# Creating a new Project

#### Lesson Objectives
In this lesson, we will learn how to create a project based on the MVC design pattern. 
We will divide our configuration, navigation (routes), logic (controllers), and our data (data model) into their separate folders to make large projects more manageable.

#### What is MVC
Model–view–controller is a software design pattern commonly used for developing user interfaces that divides the related program logic into three interconnected elements. This is done to separate internal representations of information from the ways information is presented to and accepted from the user.

The model-view-controller (MVC) design pattern specifies that an application consist of a data model, presentation information, and control information. The pattern requires that each of these be separated into different objects.

### Init Project (shortcut)
```cmd
npm init -y &&
npm i koa kao-router config js-yaml &&
mkdir config src && cd src && mkdir router controllers models middleware utils && cd .. &&
touch src/index.js src/router/index.js config/default.yaml &&
echo "// const some_name = require('some_module')" >> src/index.js &&
echo "module.exports = {\n\t// key: require('./somefile')\n}" >> src/router/index.js &&
cp src/router/index.js src/controllers/ &&
cp src/router/index.js src/models/ &&
cp src/router/index.js src/middleware/ &&
cp src/router/index.js src/utils/
```

#### Folder Structure
Below we have illustrated a tree diagram of our project.

```cmd
/project-folder
├── README.md
├── config
|  └── default.yaml
├── node_modules
├── package.json
└── src
   ├── controllers
   |  └── index.js
   ├── index.js
   ├── middleware
   |  └── index.js
   ├── models
   |  └── index.js
   ├── router
   |  └── index.js
   └── utils
      └── index.js

directory: 8 file: 9
```

steps to follow:
- create a new folder called node-project
- open it in vs-code
- run: <code>$ npm init -y</code>
- run: <code>$ npm i koa kao-router config js-yaml</code>
- run: <code>$ mkdir config src && cd src && mkdir router controllers models middleware utils && cd ..</code>
- run the code below to create <code>index.js</code> index.js files in the designated folders:
```cmd
touch src/index.js src/router/index.js config/default.yaml &&
echo "// const some_name = require('some_module')" >> src/index.js &&
echo "module.exports = {\n\t// key: require('./somefile')\n}" >> src/router/index.js &&
cp src/router/index.js src/controllers/ &&
cp src/router/index.js src/models/ &&
cp src/router/index.js src/middleware/ &&
cp src/router/index.js src/utils/ &&
```
- write the following code in your <code>config/default.yaml</code>
```yaml
server:
  protocol: http
  hostname: your-ip-address
  port: your-port
```
- write the following code in your <code>src/index.js</code>
```js
const Koa = require('koa')
const app = new Koa()
const url = require('url')
const { server } = require('config')
const router = require('./router')
const dd = (val) => console.log(val)

app.use(router.routes())

app.listen(server.port, () => {
    console.log('server running at: ' + url.format(server))
})
```
- write the following code in your <code>src/router/example.js</code>
```js
const router = require('koa-router')()
const controller = require('./../controller').example

/* ROUTES */
router.get('/users', controller.examples)

module.exports = router
```
