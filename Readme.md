1. Angular Overview and Setup (3 hours)
■ What is Angular?
■ Setting up Angular CLI and creating a new Angular project
■ Understanding the Angular architecture (Modules, Components, Services)
2. Components and Templates in Angular (4 hours)
■ Creating Angular components
■ Data binding in Angular: Interpolation, Property Binding, Event Binding,
Two-way Binding
■ Using Directives (ngIf, ngFor, etc.)
3. Services and Dependency Injection in Angular (3 hours)
■ Introduction to Angular Services
■ Dependency Injection and how it works in Angular
■ Creating and injecting services into components
4. Routing in Angular (3 hours)
■ Setting up routing in Angular
■ Configuring routes with RouterModule
■ Route guards and lazy loading in Angular
5. Forms in Angular (2 hours)
■ Template-driven forms
■ Reactive forms in Angular




That's awesome! Starting with Angular is a great decision if you're getting into modern front-end development. I'll walk you through everything **step by step**, like a mentor would. We'll keep it beginner-friendly, clear, and practical, with examples and guidance at each stage.

---

# **🧠 1. Angular Overview and Setup (3 hours)**

## 🌟 What is Angular?

Angular is a **front-end web framework** made by Google. It's used to build **single-page applications (SPAs)** — dynamic web apps that load a single HTML page and update content without reloading the page.

### ✅ Key Features:
- Component-based architecture
- Two-way data binding
- Built-in routing
- Dependency injection
- TypeScript-based

Think of Angular like a toolset to help build powerful web apps faster and in an organized way.

---

## 🔧 Setting up Angular CLI and Creating a New Project

### 📦 Step 1: Install Node.js
Download from [https://nodejs.org/](https://nodejs.org/). Angular requires Node.js to run.

### 💻 Step 2: Install Angular CLI (Command Line Interface)
Open your terminal or command prompt:
```bash
npm install -g @angular/cli
```

### 🚀 Step 3: Create a New Angular Project
```bash
ng new my-first-angular-app
cd my-first-angular-app
ng serve
```
Now open your browser and go to `http://localhost:4200` — your app is running!

---

## 🏗️ Understanding Angular Architecture

Angular is made up of:

### **1. Modules**
- Container for a set of components.
- Every app has at least one root module: `AppModule`.

### **2. Components**
- Building blocks of UI.
- A component = HTML + CSS + TS logic.

### **3. Services**
- Used to handle logic like fetching data, shared functionality.
- Injected into components.

> **Example**:  
If your app was a car:
- **Modules** are like car systems (braking, engine, etc.)
- **Components** are like parts (steering wheel, seats)
- **Services** are like behind-the-scenes work (fuel injection system)

---

# **📦 2. Components and Templates (4 hours)**

## ✅ Creating Angular Components

Run this command:
```bash
ng generate component hello-world
```

This creates a folder:
```
hello-world/
├── hello-world.component.ts (logic)
├── hello-world.component.html (template)
├── hello-world.component.css (style)
```

In `app.component.html`, you can use your new component like:
```html
<app-hello-world></app-hello-world>
```

---

## 🔄 Data Binding in Angular

### 1. **Interpolation** (`{{ }}`)
Display variables in your HTML.
```html
<p>{{ message }}</p>
```

### 2. **Property Binding** (`[ ]`)
Bind element properties.
```html
<img [src]="imageUrl">
```

### 3. **Event Binding** (`( )`)
Respond to user events.
```html
<button (click)="sayHello()">Click me</button>
```

### 4. **Two-way Binding** (`[( )]`)
Bind input values both ways.
```html
<input [(ngModel)]="username">
<p>Hello, {{ username }}!</p>
```

> To use two-way binding, import `FormsModule` in `app.module.ts`.

---

## 🧩 Using Directives

Directives help manipulate the DOM.

### `*ngIf`
Conditionally display elements:
```html
<p *ngIf="isLoggedIn">Welcome back!</p>
```

### `*ngFor`
Loop through data:
```html
<ul>
  <li *ngFor="let item of items">{{ item }}</li>
</ul>
```

---

# **💼 3. Services & Dependency Injection (3 hours)**

## 🛠️ What is a Service?

A service is a **class** that provides specific functionality (e.g., fetch data from API). Instead of writing the same logic in multiple components, you write it once in a service and **reuse it**.

---

## 💉 Dependency Injection

Instead of creating an object manually, Angular **automatically gives it to the component** when needed. This is called **Dependency Injection (DI).**

---

## 🧪 Creating and Injecting a Service

Create a service:
```bash
ng generate service data
```

In `data.service.ts`:
```ts
@Injectable({ providedIn: 'root' })
export class DataService {
  getData() {
    return ['Apple', 'Banana', 'Cherry'];
  }
}
```

Use it in a component:
```ts
constructor(private dataService: DataService) {}

ngOnInit() {
  this.items = this.dataService.getData();
}
```

---

# **🧭 4. Routing in Angular (3 hours)**

## 📍 Setting Up Routing

Add this when creating a new app:
```bash
ng new angular-routing-app --routing
```

This creates a `app-routing.module.ts`.

---

## 🛣️ Configuring Routes

In `app-routing.module.ts`:
```ts
const routes: Routes = [
  { path: 'home', component: HomeComponent },
  { path: 'about', component: AboutComponent },
];
```

In `app.component.html`:
```html
<a routerLink="/home">Home</a>
<a routerLink="/about">About</a>
<router-outlet></router-outlet>
```

---

## 🛡️ Route Guards & Lazy Loading

### Guards
Control access to routes (e.g., only logged-in users).

```bash
ng generate guard auth
```

Use it like:
```ts
{ path: 'admin', component: AdminComponent, canActivate: [AuthGuard] }
```

### Lazy Loading
Loads parts of the app only when needed:
```ts
{ path: 'products', loadChildren: () => import('./products/products.module').then(m => m.ProductsModule) }
```

---

# **📝 5. Forms in Angular (2 hours)**

## 📄 Template-driven Forms

Best for simpler forms.

In component:
```html
<form #form="ngForm" (ngSubmit)="onSubmit(form)">
  <input name="username" ngModel>
  <button type="submit">Submit</button>
</form>
```

In TS:
```ts
onSubmit(form: NgForm) {
  console.log(form.value);
}
```

---

## 🧠 Reactive Forms

Best for complex forms with validations.

In TS:
```ts
form = new FormGroup({
  name: new FormControl('')
});
```

In HTML:
```html
<form [formGroup]="form" (ngSubmit)="submit()">
  <input formControlName="name">
</form>
```

Import `ReactiveFormsModule` in your module.

---






---

# 🔶 Unit: AngularJS – Notes with Examples & Explanation

---

## ✅ 1. AngularJS Overview and Setup (Estimated Time: 3 hours)

---

## 🌟 What is Angular?

Angular is a **front-end web framework** made by Google. It's used to build **single-page applications (SPAs)** — dynamic web apps that load a single HTML page and update content without reloading the page.
### 🔹 What is AngularJS?

**AngularJS** is a **JavaScript-based open-source front-end framework** developed by **Google**. It is used to build **dynamic web applications**. Unlike plain HTML, which is static, AngularJS adds **functionality, interactivity, and dynamic data binding** to the webpage.

---

Think of Angular like a toolset to help build powerful web apps faster and in an organized way.

---

## 🔧 Setting up Angular CLI and Creating a New Project

### 📦 Step 1: Install Node.js
Download from [https://nodejs.org/](https://nodejs.org/). Angular requires Node.js to run.

### 💻 Step 2: Install Angular CLI (Command Line Interface)
Open your terminal or command prompt:
```bash
npm install -g @angular/cli
```

### 🚀 Step 3: Create a New Angular Project
```bash
ng new my-first-angular-app
cd my-first-angular-app
ng serve
```
Now open your browser and go to `http://localhost:4200` — your app is running!

---

## 🏗️ Understanding Angular Architecture

Angular is made up of:

### **1. Modules**
- Container for a set of components.
- Every app has at least one root module: `AppModule`.

### **2. Components**
- Building blocks of UI.
- A component = HTML + CSS + TS logic.

### **3. Services**
- Used to handle logic like fetching data, shared functionality.
- Injected into components.

> **Example**:  
If your app was a car:
- **Modules** are like car systems (braking, engine, etc.)
- **Components** are like parts (steering wheel, seats)
- **Services** are like behind-the-scenes work (fuel injection system)

---

### 🔸 Key Features of AngularJS:

| Feature | Description |
|--------|-------------|
| **Two-way data binding** | Automatically syncs data between model (JS code) and view (HTML) |
| **Dependency Injection** | Helps in reusing and managing code using services |
| **Directives** | Custom HTML tags to add behaviors |
| **MVC Architecture** | Separates logic (controller), data (model), and display (view) |
| **Templates** | HTML with Angular-specific syntax for binding and logic |

---

### 🔹 Setting up AngularJS

AngularJS can be used by simply adding its script file in your HTML.

```html
<!DOCTYPE html>
<html ng-app="myApp">
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>
</head>
<body>
  <div ng-controller="myCtrl">
    <h2>{{ message }}</h2>
  </div>

  <script>
    var app = angular.module('myApp', []);
    app.controller('myCtrl', function($scope) {
      $scope.message = "Hello from AngularJS!";
    });
  </script>
</body>
</html>
```

✅ **Explanation**:
- `ng-app` → Declares an AngularJS application
- `ng-controller` → Binds controller to HTML
- `{{ message }}` → Interpolation for dynamic output

---

### 🔹 AngularJS Architecture: Modules, Components, and Services

#### a. **Module**:
A container for your app. All AngularJS apps start with a module.

```js
var app = angular.module('myApp', []);
```

#### b. **Controller (Component Equivalent)**:
A function that controls app data and logic.

```js
app.controller('mainCtrl', function($scope) {
  $scope.title = "AngularJS Learning";
});
```

#### c. **Service**:
Reusable business logic or shared data across controllers.

```js
app.service('calcService', function() {
  this.square = function(x) {
    return x * x;
  };
});
```

---

## ✅ 2. Components and Templates in AngularJS

### 🔹 Creating AngularJS Components (via Directives)

In AngularJS, **components** are created using `directive()` or with the newer `.component()` method.

```js
app.component('greetingComponent', {
  template: `<h3>Hello, {{name}}!</h3>`,
  controller: function() {
    this.name = "AngularJS Student";
  }
});
```

And use it in HTML like:

```html
<greeting-component></greeting-component>
```

---

### 🔹 Data Binding in AngularJS

Data binding means connecting **model** (JS data) to the **view** (HTML UI). AngularJS supports 4 types:

---

#### 1. Interpolation (`{{ }}`)

Displays model data in HTML.

```html
<p>Hello, {{name}}</p>
```

```js
$scope.name = "Alice";
```

---

#### 2. Property Binding (`ng-src`, `ng-href`)

Use Angular expressions in HTML attributes.

```html
<img ng-src="{{imageUrl}}" />
```

```js
$scope.imageUrl = "logo.png";
```

---

#### 3. Event Binding (`ng-click`, `ng-change`)

Handles user input/events.

```html
<button ng-click="sayHello()">Click Me</button>
```

```js
$scope.sayHello = function() {
  alert("Hello!");
};
```

---

#### 4. Two-Way Binding (`ng-model`)

Syncs data between input fields and variables.

```html
<input type="text" ng-model="username">
<p>Your name is: {{username}}</p>
```

✅ Changes in input are **instantly reflected** in the model and vice versa.

---

### 🔹 Using Built-in Directives (`ngIf`, `ngFor`, etc.)

Directives extend HTML by adding behavior.

---

#### a. `ng-if`

Conditionally renders elements.

```html
<p ng-if="isLoggedIn">Welcome back!</p>
```

```js
$scope.isLoggedIn = true;
```

---

#### b. `ng-repeat` (like loop or `ngFor`)

Loops through collections (arrays).

```html
<ul>
  <li ng-repeat="fruit in fruits">{{fruit}}</li>
</ul>
```

```js
$scope.fruits = ['Apple', 'Banana', 'Cherry'];
```

---

#### c. `ng-show` / `ng-hide`

Show or hide based on condition.

```html
<div ng-show="isAdmin">Admin Panel</div>
```

```js
$scope.isAdmin = true;
```

---

#### d. `ng-model`

Used for **two-way data binding** with input fields.

```html
<input type="text" ng-model="email" />
<p>Your email: {{email}}</p>
```

---

## ✅ Summary Table (Quick Reference)

| Concept | Example | Description |
|--------|---------|-------------|
| Module | `angular.module('app', [])` | Root of AngularJS app |
| Controller | `app.controller(...)` | Controls logic and data |
| Service | `app.service(...)` | Reusable functions |
| Interpolation | `{{name}}` | Display value in HTML |
| Event Binding | `ng-click="action()"` | Handle user events |
| Two-way Binding | `ng-model="val"` | Sync input and variable |
| ng-if | `ng-if="condition"` | Conditional rendering |
| ng-repeat | `ng-repeat="item in list"` | Loop through list |

---

## ✅ Real-World Mini Example (All Concepts Together)

```html
<!DOCTYPE html>
<html ng-app="studentApp">
<head>
  <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular.min.js"></script>
</head>
<body ng-controller="studentCtrl">
  <h2>Welcome {{student.name}}</h2>
  <input type="text" ng-model="student.name">
  <button ng-click="reset()">Reset</button>

  <ul>
    <li ng-repeat="sub in student.subjects">{{sub}}</li>
  </ul>

  <p ng-if="student.name.length > 0">Name is set!</p>

  <script>
    var app = angular.module('studentApp', []);
    app.controller('studentCtrl', function($scope) {
      $scope.student = {
        name: "John",
        subjects: ["Math", "Science", "English"]
      };

      $scope.reset = function() {
        $scope.student.name = "";
      };
    });
  </script>
</body>
</html>
```

---

# 🔶 3. Services and Dependency Injection in AngularJS  

---

## 🔹 Introduction to AngularJS Services

### 🔸 What is a Service?

In AngularJS, a **service** is a reusable component that contains **logic or data** which can be shared across different parts of the application (like controllers or directives).  
It is commonly used for:
- Business logic
- API calls
- Shared data storage

Services help keep your code **modular, clean, and DRY** (Don’t Repeat Yourself).

---

### 🔸 Types of Services in AngularJS

| Type | Description |
|------|-------------|
| `$http` | Makes HTTP requests |
| `$location` | Access browser URL |
| `$timeout`, `$interval` | Set timeouts or intervals |
| `Custom services` | User-defined for specific app logic |

---

### 🔹 Creating a Custom Service

```javascript
var app = angular.module('myApp', []);

app.service('mathService', function() {
  this.square = function(x) {
    return x * x;
  };
});
```

---

### 🔹 Using a Service in Controller (Injecting it)

```javascript
app.controller('myCtrl', function($scope, mathService) {
  $scope.result = mathService.square(5);  // Outputs: 25
});
```

✅ The **service is injected** into the controller automatically by AngularJS.

---

## 🔹 Dependency Injection (DI) in AngularJS

### 🔸 What is Dependency Injection?

**Dependency Injection** is a design pattern where an object receives its dependencies from an external source, instead of creating them internally.  
In AngularJS, DI makes components **easily testable, modular, and maintainable**.

---

### 🔸 How AngularJS DI Works

AngularJS injects services into your components (controllers, directives, filters) by **matching parameter names**.

```js
app.controller('exampleCtrl', function($scope, $http, myService) {
  // All dependencies injected automatically
});
```

⚠️ Be careful: **parameter names must match the service names** exactly.

---

### 🔹 Best Practices

- Always use services for shared logic.
- Keep controllers "thin" and services "fat" (put logic in services).

---

## 🔶 4. Routing in AngularJS  

---

### 🔹 Why Routing is Needed?

Routing allows you to build **Single Page Applications (SPAs)**. Instead of loading new HTML pages from the server, AngularJS changes the **content dynamically** based on the URL using routing.

---

### 🔹 Setting Up Routing

You need to include the `angular-route` module.

```html
<script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.8.2/angular-route.min.js"></script>
```

---

### 🔹 Configure Your App to Use Routing

```js
var app = angular.module("myApp", ["ngRoute"]);

app.config(function($routeProvider) {
  $routeProvider
    .when("/home", {
      templateUrl: "home.html",
      controller: "homeCtrl"
    })
    .when("/about", {
      templateUrl: "about.html",
      controller: "aboutCtrl"
    })
    .otherwise({
      redirectTo: "/home"
    });
});
```

---

### 🔹 Router Example Folder Structure

```
/index.html
/home.html
/about.html
/app.js
```

---

### 🔹 Sample Controllers

```js
app.controller("homeCtrl", function($scope) {
  $scope.title = "Welcome to Home Page";
});

app.controller("aboutCtrl", function($scope) {
  $scope.title = "About Us";
});
```

---

### 🔹 Adding Route Links in HTML

```html
<a href="#!/home">Home</a>
<a href="#!/about">About</a>

<div ng-view></div>
```

- `ng-view` is the placeholder where the routed content is displayed.

---

## 🔹 Route Guards in AngularJS

Unlike Angular (2+), AngularJS doesn’t have built-in **route guards**, but we can simulate similar behavior using `$routeChangeStart`:

```js
app.run(function($rootScope, $location, authService) {
  $rootScope.$on('$routeChangeStart', function(event, next) {
    if (!authService.isLoggedIn()) {
      $location.path('/login');
    }
  });
});
```

---

## 🔹 Lazy Loading (Workaround in AngularJS)

AngularJS doesn’t support **native lazy loading**, but you can use libraries like **ocLazyLoad**:

```js
app.config(function($routeProvider) {
  $routeProvider
    .when('/dashboard', {
      templateUrl: 'dashboard.html',
      controller: 'dashboardCtrl',
      resolve: {
        load: function($ocLazyLoad) {
          return $ocLazyLoad.load('dashboardCtrl.js');
        }
      }
    });
});
```

---

## ✅ Recap Table

| Feature | Use |
|--------|-----|
| `service()` | Define reusable logic |
| `Dependency Injection` | Inject services into controllers |
| `$routeProvider` | Configure routes |
| `ng-view` | Display routed template |
| `$routeChangeStart` | Secure routes manually |
| `ocLazyLoad` | Lazy load controllers or files |

---

### ✅ Mini Routing App Example

```html
<body ng-app="routerApp">
  <a href="#!/home">Home</a>
  <a href="#!/about">About</a>

  <div ng-view></div>

  <script>
    var app = angular.module("routerApp", ["ngRoute"]);

    app.config(function($routeProvider) {
      $routeProvider
        .when("/home", {
          template: "<h2>Welcome to Home</h2>"
        })
        .when("/about", {
          template: "<h2>About AngularJS</h2>"
        })
        .otherwise({ redirectTo: "/home" });
    });
  </script>
</body>
```

---

# 🔶 Forms in Angular (Template-Driven & Reactive)  


---

## ✅ 1. Template-Driven Forms (AngularJS / Angular 2+)

---

### 🔹 What is a Template-Driven Form?

A **template-driven form** is defined mostly in HTML using Angular directives like `ngModel`, `required`, `ngSubmit`, etc.  
It’s suitable for **simple forms** and uses **two-way data binding**.

---

### 🔸 Key Features

| Feature | Description |
|---------|-------------|
| `ngModel` | Binds form input to model |
| `required`, `minlength`, etc. | Built-in validations |
| `ngForm` | Automatically added to `<form>` |
| `#formRef="ngForm"` | Template reference variable |

---

### 🔹 Example – Template-Driven Form

```html
<form name="userForm" ng-submit="submitForm()" novalidate>
  <label>Name:</label>
  <input type="text" name="name" ng-model="user.name" required>
  <span ng-show="userForm.name.$error.required && userForm.name.$touched">Name is required.</span>

  <label>Email:</label>
  <input type="email" name="email" ng-model="user.email" required>
  <span ng-show="userForm.email.$error.required && userForm.email.$touched">Email is required.</span>

  <button type="submit">Submit</button>
</form>
```

```js
$scope.submitForm = function() {
  if ($scope.userForm.$valid) {
    alert("Form submitted!");
  }
};
```

---

### 🔸 Form States and Properties

| Property | Description |
|----------|-------------|
| `$valid` | All validations passed |
| `$invalid` | At least one validation failed |
| `$touched` | User has focused & left input |
| `$pristine` | Input has not been modified |
| `$dirty` | Input has been changed |

---

## ✅ 2. Reactive Forms (Only in Angular 2+)

Reactive Forms (also called **Model-Driven Forms**) are **defined in TypeScript** and provide better scalability and testability.

> ⚠️ Note: **Reactive Forms are not available in AngularJS 1.x**. They are used only in **Angular 2 and later**.

---

### 🔸 Key Concepts

| Term | Description |
|------|-------------|
| `FormControl` | Tracks individual form input |
| `FormGroup` | Groups multiple controls |
| `Validators` | Add validation rules |
| `formControlName` | Binds control to template |

---

### 🔹 Basic Example – Reactive Form

```ts
import { Component } from '@angular/core';
import { FormGroup, FormControl, Validators } from '@angular/forms';

@Component({
  selector: 'app-profile',
  template: `
    <form [formGroup]="profileForm" (ngSubmit)="onSubmit()">
      <input formControlName="firstName">
      <div *ngIf="profileForm.get('firstName').invalid">First name is required</div>

      <input formControlName="email">
      <div *ngIf="profileForm.get('email').invalid">Enter valid email</div>

      <button type="submit">Submit</button>
    </form>
  `
})
export class ProfileComponent {
  profileForm = new FormGroup({
    firstName: new FormControl('', Validators.required),
    email: new FormControl('', [Validators.required, Validators.email])
  });

  onSubmit() {
    console.log(this.profileForm.value);
  }
}
```

---

### 🔸 Why Choose Reactive Forms?

| Feature | Template-Driven | Reactive |
|--------|------------------|----------|
| Simplicity | Easier for small forms | Better for complex logic |
| Validation | In template | In TypeScript |
| Testability | Limited | Highly testable |
| Control | Less programmatic control | Full programmatic control |

---

### ✅ Summary Table

| Feature | Template-Driven | Reactive |
|--------|------------------|----------|
| Defined In | HTML templates | Component (TS code) |
| Suitable For | Simple forms | Large, complex forms |
| Form Binding | `ngModel` | `formControlName` |
| Validation Location | Template-based | Code-based |

---

## ✅ Conclusion

- **Use Template-Driven Forms** when your form is simple, small, and requires rapid development.
- **Use Reactive Forms** when you need advanced validation, better control, or testable forms.

---
