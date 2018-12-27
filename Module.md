## Module
  
**ng g m User**

**ng g c user/login**

**routes.ts**

```javascript

import {Routes} from '@angular/router'
import {LoginComponent} from './user/login/login.component'

export const appRoutes:Routes=[
    {path:'user/login',component:LoginComponent},
]

```

**app.module.ts**

```javascript

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';

import { LoginComponent } from './user/login/login.component';
import {appRoutes} from './routes';
import { RouterModule } from '@angular/router';

@NgModule({

	declarations: [
		AppComponent,
		LoginComponent
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

URL : http://localhost:4200/user/login
