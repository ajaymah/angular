# angular
### 1- What is Angular data binding types ###
Angular provides four types of data binding:  
- **Interpolation ({{ }})** – Displays component data in the template.  
- **Property Binding ([ ])** – Binds component values to DOM properties, such as src or disabled.  
- **Event Binding (( ))** – Handles user events like clicks or input and invokes component methods.  
- **Two-Way Binding ([(ngModel)]**) – Combines property and event binding to keep the component and UI synchronized.  
  
> Note: Interpolation and property binding are one-way from component to view,
> event binding is one-way from view to component, and two-way binding synchronizes data in both directions.
```javascript
| Data Binding     | Syntax                | Direction        | Example                  |
| ---------------- | --------------------- | ---------------- | ------------------------ |
| Interpolation    | `{{ value }}`         | Component → View | `{{ name }}`             |
| Property Binding | `[property]="value"`  | Component → View | `[src]="imageUrl"`       |
| Event Binding    | `(event)="method()"`  | View → Component | `(click)="save()"`       |
| Two-Way Binding  | `[(ngModel)]="value"` | Both             | `[(ngModel)]="username"` |

```
### 2- what is directive in Angular, type of directive ###  
A directive in Angular is a class that adds behavior to DOM elements.
Angular provides three types of directives:  
- **Component Directives** – Components with their own template, created using **@Component**.
- **Structural Directives** – Modify the DOM by adding or removing elements, such as *ngIf, *ngFor, and *ngSwitch.
- **Attribute Directives** – Modify the appearance or behavior of existing elements without changing the DOM structure, such as **ngClass**, **ngStyle**, or custom attribute directives.

### 3- What is a Pipe in Angular? ###   
A Pipe is a feature in Angular that **transforms data before displaying** it in the template.   
Pipes do not modify the original data; they only change how the data is displayed.  
**Pure Pipe?** - By default, all Angular pipes are pure. (primitive value, or input refrence)  
Example:- date, currency, uppercase, and percent  
**Impure Pipe?** - An Impure Pipe executes during every **change detection cycle**, even if the input reference hasn't changed.

### 4- What is Angular Change Detection? ###  
Change Detection is the proces, Whenever data is changes in Angular, Angular automatically updates the DOM through change detection.
**How Does Angular Perform Change Detection?**  
By default, Angular starts checking from the root component and traverses the component tree.
This is the Default Change Detection Strategy.  
**Angular provides two strategies:**  
Default    
OnPush  
```javascript
import { ChangeDetectionStrategy } from '@angular/core';

@Component({
  selector: 'app-user',
  changeDetection: ChangeDetectionStrategy.OnPush
})
export class UserComponent {}
```
With **OnPush**, Angular does not check the component on every change detection cycle.
It checks the component only when specific triggers occur.

**When Does OnPush Run?**   
1- @Input() Reference Changes  
2- An Event Occurs Inside the Component
3- An Observable Emits (used with async pipe)
4- A Signal Changes
