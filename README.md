## install bootsrap

Go to your command-line interface and install Bootstrap 4 via npm as follows:

 ```html
  npm install --save bootstrap
``` 
Next, you also need to install jQuery using the following command:
 ```html
 npm install --save jquery
``` 
#### Method 1
Open the angular.json file of your project and include:
 ```html
   "styles": [
      "./node_modules/bootstrap/dist/css/bootstrap.css",
      "src/styles.css"              
    ],
    "scripts": [
      "./node_modules/jquery/dist/jquery.js",
      "./node_modules/bootstrap/dist/js/bootstrap.js"
    ]
```


