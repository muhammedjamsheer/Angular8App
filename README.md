## Install bootsrap

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

#### Method 3
We can also use the styles.css file to add the CSS file of Bootstrap to our project.
 ```html
@import "~bootstrap/dist/css/bootstrap.css"
```

## Toaster Notification in Angular 8
#### Step 1 : Install Toastr
 ```html
  npm install ngx-toastr@11.3.3 
```
 ```html
  npm install @angular/animations --save
```
Open the angular.json file of your project and include:
 ```html
 .....
  "styles": [
    "node_modules/ngx-toastr/toastr.css",
    "src/styles.css"
  ],
.....
```

#### Step 2 : Import Module
In this step, we need to import ToastrModule and BrowserAnimationsModule to app.module.ts file
###### src/app/app.module.ts
 ```html
import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
  
import { AppComponent } from './app.component';
import { BrowserAnimationsModule } from '@angular/platform-browser/animations';
import { ToastrModule } from 'ngx-toastr';
  
@NgModule({
  declarations: [
    AppComponent
  ],
  imports: [
    BrowserModule,
    BrowserAnimationsModule,
    ToastrModule.forRoot()
  ],
  providers: [],
  bootstrap: [AppComponent]
})
export class AppModule { }
```

#### Step 3 : Create Service for Notification

Here, we will create separate notification for Toastr. so you can use showSuccess(), showError(), showInfo() and showWarning() in any component.

###### src/app/notification.service.ts
  ```html
import { Injectable } from '@angular/core';
import { ToastrService } from 'ngx-toastr';

@Injectable({
  providedIn: 'root'
})
export class NotificationService {
  
  constructor(private toastr: ToastrService) { }
  
  showSuccess(message, title){
      this.toastr.success(message, title)
  }
  showError(message, title){
      this.toastr.error(message, title)
  }
  showInfo(message, title){
      this.toastr.info(message, title)
  }
  showWarning(message, title){
      this.toastr.warning(message, title)
  } 
}
  ```

