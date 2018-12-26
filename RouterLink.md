## Router Link

**my-first-component.component.html**

```html

<h2>Employee Details</h2>
<div *ngFor = "let employee of employee1" [routerLink]="['/employees',employee.id]">
{% raw %} {{employee.id}} {% endraw %}<br/>
{% raw %} {{employee.name}} {% endraw %}
<hr/>
</div>

```
