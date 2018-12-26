## Routing with Parameter

**my-second-component.component.ts**

```javascript

import { Component, OnInit } from '@angular/core';
import {ActivatedRoute} from '@angular/router';

@Component({
	selector: 'app-my-second-component',
	templateUrl: './my-second-component.component.html',
	styleUrls: ['./my-second-component.component.css']
})

export class MySecondComponentComponent implements OnInit {

	employee:any

	constructor(private route:ActivatedRoute) { }

	ngOnInit() {
		this.employee = this.employee1[this.route.snapshot.params['id']]
	}

	employee1=[{
	    id:0,
	    name:'Akshay Patel'
	  },
	  {
	    id:1,
	    name:'Panth Patel'
	  },
	  {
	    id:2,
	    name:'Jemin Patel'
	  }]
}

```

**my-second-component.component.html**

```html

<h2>Employee Details</h2>
{% raw %} {{employee.id}} {% endraw %}<br/>
{% raw %} {{employee.name}} {% endraw %}
<hr/>

```

**routes.ts**

```javascript

import {Routes} from '@angular/router'
import { MySecondComponentComponent } from './my-second-component/my-second-component.component';
import { MyFirstComponentComponent } from './my-first-component/my-first-component.component';

export const appRoutes:Routes=[

	{path:'employees',component:MyFirstComponentComponent},

	{path:'employees/:id',component:MySecondComponentComponent},

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
import { MySecondComponentComponent } from './my-second-component/my-second-component.component';

@NgModule({

	declarations: [
		AppComponent,
		MyFirstComponentComponent,
		MySecondComponentComponent
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
