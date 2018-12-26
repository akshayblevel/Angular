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

	employee={
		id:1,
		name:'Akshay Patel'
	}
}

```
**my-first-component.component.html**

```html
<h2>Employee Details</h2>
<div>
<div>
{{employee.id}}
<hr/>
{{employee.name}}
</div>
</div>

```
**app.component.html**

```html
<app-my-first-component></app-my-first-component>
```
