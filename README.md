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
 ```javascript
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
```javascript
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

#### Step 4 : Updated View File

Now here, we will updated our html file. we will create simple four buttons for alert messages.

###### src/app/app.component.html
```html
<button (click)="showToasterSuccess()">
    Success Toaster
</button>
  
<button (click)="showToasterError()">
    Error Toaster
</button>
  
<button (click)="showToasterInfo()">
    Info Toaster
</button>
  
<button (click)="showToasterWarning()">
    Warning Toaster
</button>
```

#### Step 5 : Use Component ts File
Now we need to update our component.ts file here we will use notification service and call alert.
###### src/app/app.component.ts
```javascript
import { Component } from '@angular/core';

import { NotificationService } from './notification.service'
  
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  
  constructor(private notifyService : NotificationService) { }
  
  showToasterSuccess(){
      this.notifyService.showSuccess("Data shown successfully !!", "ItSolutionStuff.com")
  }
  
  showToasterError(){
      this.notifyService.showError("Something is wrong", "ItSolutionStuff.com")
  }
  
  showToasterInfo(){
      this.notifyService.showInfo("This is info", "ItSolutionStuff.com")
  }
  
  showToasterWarning(){
      this.notifyService.showWarning("This is warning", "ItSolutionStuff.com")
  }
}
```

## Create Dummy Database using JSON Server
Run the below command in the terminal.

```html
 npm install Json-server 
 ```
 Now place data.json file in folder db.json with following data:
 ```html
  {
"students": [
    {
      "id": 1,
      "name": "Enola Rowe",
      "class": "tony@mcu.com",
      "address": "131 Oswaldo Street"
    },{
      "id": 2,
      "name": "Timmothy Lueilwitz",
      "age": "15",
      "address": "37137 Abbigail Lock"
    }
  ]
} 
 ```
 Running the server in two ways

#### 1. Direct Command execution
You can run server response by running following NPM command:
 ```html
 json-server --watch db.json
 ```
 #### 2. Adding json file manually in package.json
In package.json, add the below code to run json-server with short code.

"json:server": "json-server --watch db.json",
  ```html
"scripts": {
  "ng": "ng",
  "start": "ng serve",
  "build": "ng build",
  "json:server": "json-server --watch db.json",
  "test": "ng test",
  "lint": "ng lint",
  "e2e": "ng e2e"
}, 
 ```
 
 Now, run the server
 ```html
 npm run json:server 
 ```
Your JSON Server will be running on port 3000. The below data will be shown in the terminal

http://localhost:3000/students
 
