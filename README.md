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

#### Method 2
include Bootstrap files from node_modules/bootstrap using the index.html file.
 ```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Angular Bootstrap 4 Examples</title>
  <base href="/">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <link rel="icon" type="image/x-icon" href="favicon.ico">
  <link rel="stylesheet" href="../node_modules/bootstrap/dist/css/bootstrap.css">

</head>
<body>
  <app-root></app-root>
  <script src="../node_modules/jquery/dist/jquery.js"></script>
  <script src="../node_modules/bootstrap/dist/js/bootstrap.js"></script>    
</body>
</html>
```


