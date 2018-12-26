## Safe Navigation Operator

This will not throw an exception even though employee is undefined.

**my-first-component.component.html**

```html

<div *ngFor = "let employee of employee1">
{% raw %} {{employee?.id}} {% endraw %}<br/>
{% raw %} {{employee?.name}} {% endraw %}
<hr/>
</div>

```
