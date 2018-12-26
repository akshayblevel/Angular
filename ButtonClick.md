## Button Click Event

**my-second-component.component.html**

```html

<div>
<button class="btn btn-primary" (click)="handleClickMe()" >Click Me!</button>
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

	constructor() { }

	ngOnInit() {
	}

	handleClickMe(){
		console.log("Clicked!")
	}
}

```
