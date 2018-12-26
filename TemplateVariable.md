## Using Template Variables To Interact with Child Components

**Method**

**my-first-component.component.html**

```html

<app-my-second-component #secondComponent></app-my-second-component>
<button (click)="secondComponent.TestMethod()">TestMethod of SecondComponent </button>

```

**my-second-component.component.ts**

```javascript

import { Component, OnInit } from '@angular/core';

@Component({
	selector: 'app-my-second-component',
	templateUrl: './my-second-component.component.html',
	styleUrls: ['./my-second-component.component.css']
})

export class MySecondComponentComponent implements OnInit {

	constructor() { }

	ngOnInit() {
	}

	TestMethod(){
		console.log("TestMethod of Second Component is called by First Component")
	}
}

```

**Property**

**my-first-component.component.html**

```html

<app-my-second-component #secondComponent></app-my-second-component>
<h3>{{secondComponent.TestPropery}}</h3>

```

**my-second-component.component.ts**

```javascript

import { Component, OnInit} from '@angular/core';

@Component({
	selector: 'app-my-second-component',
	templateUrl: './my-second-component.component.html',
	styleUrls: ['./my-second-component.component.css']
})

export class MySecondComponentComponent implements OnInit {

	TestPropery:any = 'Akshay Patel'

	constructor() { }

	ngOnInit() {
	}
}

```
