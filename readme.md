nodejs is a runtime environment for javascript also comes with extra APIs.
it's Asynchronous also non-blocking I/O.

### Questions:-
1. it's webserver?
no but if you used express you can make webserver.

2. why node webserver?
for heavy I/O (streaming app)

### chapter 1(Modules,FS,NPM,package.json,REPL)

install node.js from [node](https://nodejs.org/en)
check node globally install or not using `node -v`
check npm globally install or not using `npm -v`

let's type `node` in terminal then node repl interface is running

#### modules :-

you can create a function and use outside the file using modules(import,export)
most of time we are using es6 but for now i am give you common.js syntax
##### module.js
```
function sum(a, b) {
    return a + b
}

exports.sum = sum
```

##### index.js
```
const { sum } = require("./module")

console.log(sum(2,3))
```
#### package.json
it's a json file that contains packages also manages.
let's create package.json file and add type module to it.
now we can use es6 syntax 

#### FS module
```
const fs = require('fs') //import fs module

const txt = fs.readFileSync('demo.txt','utf-8') //readfile synchronously in utf-8 format
console.log(txt) //output the file
```

now let's see asynchronous 
```
const fs = require('fs')

const txt = fs.readFile('demo.txt','utf-8',(error,txt) =>{
    console.log(txt)
})
```

#### npm
`npm init` from these we can initialize node file.
now let's install npm package using `npm install <package-name>`
we can see packages in package.json file inside dependencies

we have also dev dependencies that only used in development 
for example we have nodemon we can install it using `npm install nodemon --save-dev`
and then we are put in scripts so we can run using start.
```
"scripts:" {
    "start": "nodemon index.js",
}
```
to run these we can type `npm run start`

if we want to install package in our localmachine we can type `npm install -g nodemon`

version names :-
~4.18.1
sign is strict first digit represents major version second represents minor version last represents patch version.
^4.18.1
sign is able to take updates for minor updates not major. 

if we type `npm install` then it will install all dependencies from package.json file
to remove package we can type `npm uninstall <package-name>`
note that don't push node_modules in git for that we can use .gitignore file