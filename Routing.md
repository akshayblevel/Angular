## Routing

**my-first-component.component.ts**

```javascript

import { Component, OnInit } from '@angular/core';

@Component({
	selector: 'app-my-first-component',
	templateUrl: './my-first-component.component.html',
	styleUrls: ['./my-first-component.component.css']
})

export class MyFirstComponentComponent implements OnInit {
	
	constructor() { }

	ngOnInit() {
	}

	employee1=[{
	    id:1,
	    name:'Akshay Patel'
	  },
	  {
	    id:2,
	    name:'Panth Patel'
	  },
	  {
	    id:3,
	    name:'Jemin Patel'
	  }]
}

```

**my-first-component.component.html**

```html

<h2>Employee Details</h2>

<div *ngFor = "let employee of employee1">
	{% raw %} {{employee.id}} {% endraw %}<br/>
	{% raw %} {{employee.name}} {% endraw %}
<hr/>
</div>

```

**routes.ts**

```javascript

import {Routes} from '@angular/router'
import { MyFirstComponentComponent } from './my-first-component/my-first-component.component';

export const appRoutes:Routes=[
	
	{path:'employees',component:MyFirstComponentComponent},

	{path:'',redirectTo:'/employees',pathMatch:'full'}
]

```

**app.module.ts**

```javascript

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
import { MyFirstComponentComponent } from './my-first-component/my-first-component.component';
import {appRoutes} from './routes';
import { RouterModule } from '@angular/router';

@NgModule({

declarations: [
	AppComponent,
	MyFirstComponentComponent
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

**app.component.html**

```html

<router-outlet></router-outlet>

```
