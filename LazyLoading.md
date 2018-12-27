## Lazy Loaded Module

**ng g m User**

**ng g c user/login**

**routes.ts**

```javascript

import { Routes } from "@angular/router";

export const appRoutes:Routes=[
{ path: 'user', loadChildren: './user/user.module#UserModule' }
]

```

**app.module.ts**
```javascript

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
import { RouterModule } from '@angular/router';
import { appRoutes} from './routes';

@NgModule({
	
	declarations: [
		AppComponent
	],

	imports: [
		BrowserModule,
		RouterModule.forRoot(appRoutes)
	],

	providers: [],

	bootstrap: [AppComponent]

})
export class AppModule { }

```

**user.routes.ts**
```javascript

import { LoginComponent } from "./login.component";
export const userRoutes=[
{path:'login',component:LoginComponent}
] 

```

**user.module.ts**

```javascript

import { NgModule } from '@angular/core';
import { CommonModule } from '@angular/common';
import {RouterModule} from '@angular/router';
import { LoginComponent } from './login.component';
import { userRoutes } from './user.routes';
import {FormsModule} from '@angular/forms';

@NgModule({

	imports: [
		CommonModule,
		FormsModule,
		RouterModule.forChild(userRoutes)
	],

	declarations: [
		LoginComponent
	]
})

export class UserModule { }

```


