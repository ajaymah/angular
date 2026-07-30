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
