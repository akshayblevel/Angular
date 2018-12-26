## Service

**ng g s EmployeeService**

**employee-service.service.ts**

```javascript

import { Injectable } from '@angular/core';

@Injectable({
	providedIn: 'root'
})

export class EmployeeServiceService {
	
	constructor() { }

	getEmployees()
	{
		return EMPLOYEE
	}
}

const EMPLOYEE = [
	{
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
	}
]

```

**app.module.ts**

```javascript

import { BrowserModule } from '@angular/platform-browser';
import { NgModule } from '@angular/core';
import { AppComponent } from './app.component';
import { MyFirstComponentComponent } from './my-first-component/my-first-component.component';
import { EmployeeServiceService } from './Services/employee-service.service';


@NgModule({

	declarations: [
		AppComponent,
		MyFirstComponentComponent,
		MySecondComponentComponent
	],

	imports: [
		BrowserModule
	],

	providers: [EmployeeServiceService],

	bootstrap: [AppComponent]
})

export class AppModule { }

```

**my-first-component.component.ts**

```javascript

import { Component, OnInit } from '@angular/core';
import { EmployeeServiceService } from '../Services/employee-service.service';

@Component({
	selector: 'app-my-first-component',
	templateUrl: './my-first-component.component.html',
	styleUrls: ['./my-first-component.component.css']
})

export class MyFirstComponentComponent implements OnInit {
	employee : any[]

	constructor(private employeeService : EmployeeServiceService) 
	{
	}

	ngOnInit() {
		this.employee = this.employeeService.getEmployees()
	}
}

```

**my-first-component.component.html**

```html

<div *ngFor = "let employee of employee">
{% raw %} {{employee.id}} {% endraw %}<br/>
{% raw %} {{employee.name}} {% endraw %}
<hr/>
</div>

```
