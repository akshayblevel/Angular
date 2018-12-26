## Communication with child component using @Input

**my-second-component.component.html**

```html

<h2>Employee Details</h2>
<div>
<div>
	{% raw %} {{ employee.id }} {% endraw %}
<hr/>
	{% raw %} {{ employee.name }} {% endraw %}
</div>
</div>

```

**my-second-component.component.ts**

```javascript

import { Component, OnInit, Input } from '@angular/core';

@Component({
	selector: 'app-my-second-component',
	templateUrl: './my-second-component.component.html',
	styleUrls: ['./my-second-component.component.css']
})

export class MySecondComponentComponent implements OnInit {

	@Input() employee:any

	constructor() { }
	
	ngOnInit() {
	}
}

```

**my-first-component.component.html**

```html

<app-my-second-component [employee]="employee1"></app-my-second-component>

```

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

	employee1={
		id:1,
		name:'Akshay Patel'
	}
}

```

**app.component.html**

```html

app.component.html

```
