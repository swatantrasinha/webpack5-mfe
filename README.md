# webpack5-mfe
--------------

<details>
<summary> Section-01</summary>
<details>
<summary> Section-01 - Part1 : Getting Started </summary>

 <details>
<summary> Screenshots to understand webpack </summary>
1. Why Webpack ?
<img width="927" alt="01_why-webpack" src="https://github.com/user-attachments/assets/dbf158f2-f50a-4d2c-bbe9-360db12d4b7b">
			
2. Modules
<img width="1021" alt="02_birth_of_modules" src="https://github.com/user-attachments/assets/29160f4d-3171-4289-a6f6-5e5732e6610f">
			
3. Use of Webpack
<img width="1239" alt="03_use-of-webpack" src="https://github.com/user-attachments/assets/1f43e5ab-b5e3-4904-a0d6-e43a4074d9ad">
			
4. How webpack works ?
<br />
<img width="446" alt="04_how-webpack-works_a" src="https://github.com/user-attachments/assets/26b28e68-1fff-4add-b5c3-e36a08403010">
<br />
<img width="1501" alt="04_how-webpack-works_b" src="https://github.com/user-attachments/assets/15696a7f-3c59-4066-bb83-f5c4432ce36c">
<br />

</details>

<details>
<summary> Lets do some practical  </summary>
Steps :   
<br />
			
> npm init -y <br />
> npm i --save-dev webpack webpack-cli <br />
> npm i --save lodash <br />

Lets create 4 files
- create folder "src" parallel to package.json
- add index.html and index.js inside src folder
- create webpack.config.js file
<br />

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
			
```javascript
			
const path= require('path')
			
module.exports= {
    entry: "./src/index.js",
    output: {
        filename: "bundle.js",
        path: path.resolve(__dirname, "dist")
    }
}
```

</details>
	
> npm i <br />


> npm run build

Now open html file with live server and click on button "Click Me"
</details>

<details>
<summary> Section-01 - Part2 : CommonJS-Modules </summary>
<img width="516" alt="Section1-Part2-Modules-In-Javascript" src="https://github.com/user-attachments/assets/2c19d441-9d75-4f41-af67-29f5734de213">

	
</details>


</details>



