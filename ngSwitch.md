## *ngSwitch

**my-first-component.component.html**

```html

<div *ngFor = "let employee of employee1">
  <div [ngSwitch]="employee.id">
   {% raw %} {{employee.id}} {% endraw %}<br/>
      <span *ngSwitchCase="1">
        Odd Number
      </span>
      <span *ngSwitchCase="2">
        Even Number
      </span>
      <span *ngSwitchDefault>
        Not Defined
      </span>
  </div>
  {% raw %} {{employee.name}} {% endraw %}
  <hr/>
</div>

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

	employee1=[{
		id:1,
		name:'Akshay Patel'
	},
	{
		id:2,
		name:'Panth Patel'
	}]
}

```
