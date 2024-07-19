# webpack5-mfe
--------------

<details>
<summary> Section-01</summary>
Steps : 
  
<br />

> npm init -y <br />
> npm i --save-dev webpack webpack-cli <br />
> npm i --save lodash <br />

<details>
  <summary> 1. package.json </summary>
<br />
make below changes in scripts <br />
  
>  "build": "webpack --config webpack.config.js --mode development"

```javascript

{
  "name": "01_Getting_Started",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "build": "webpack --config webpack.config.js --mode development"
  },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "webpack": "^5.88.2",
    "webpack-cli": "^5.1.4"
  },
  "dependencies": {
    "lodash": "^4.17.21"
  }
}

```
</details>


<details>
  <summary> 2. index.html </summary>

```javascript

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Webpack</title>
</head>
<body>
    <h1 id="header"> Hey  this is my first webpack application</h1>
    <ul id="shopping-list"></ul>
    <button id="button1">Click Me</button>
</body>
<script src="../dist/bundle.js"></script>
</html>
```
</details>

<details>
<summary> 3. index.js </summary>

  ```javascript  

import _ from "lodash";

document.getElementById('button1').addEventListener('click',function() {
    const el= document.getElementById('header')
    el.innerHTML= "Hey I have updated the code"
    
    const listItems= ['Apples', 'Mangoes', 'Oranges']
    const ulEle= document.getElementById('shopping-list')
    _.forEach(listItems, function(item) {
        const tempEle= document.createElement('li')
        tempEle.innerHTML= item
        ulEle.appendChild(tempEle)
    })
})

```
</details>

<details>
<summary> 4. webpack.config.js </summary>

const path= require('path')

module.exports= {
    entry: "./src/index.js",
    output: {
        filename: "bundle.js",
        path: path.resolve(__dirname, "dist")
    }
}

</details>

</details>



