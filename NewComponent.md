## Create New Component

**ng g c MyFirstComponent**

If we have child module then we need to move import from app.module.ts to childmodule.module.ts

app.module.ts

```javascript
import { MyFirstComponentComponent } from './my-first-component/my-first-component.component';

@NgModule({
	
	declarations: [
		AppComponent,
		MyFirstComponentComponent
	],

	imports: [
		BrowserModule
	],

	providers: [],

	bootstrap: [AppComponent]
})

export class AppModule { }
```

my-first-component.component.ts

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

}

