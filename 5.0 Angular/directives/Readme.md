# Directives

Angular templates are dynamic. When Angular renders them, it transforms the DOM according to the instructions given by directives. A directive is a class with a @Directive() decorator.

A component is technically a directive. However, components are so distinctive and central to Angular applications that Angular defines the @Component() decorator, which extends the @Directive() decorator with template-oriented features.

In addition to components, there are two other kinds of directives: structural and attribute. Angular defines a number of directives of both kinds, and you can define your own using the @Directive() decorator.

Just as for components, the metadata for a directive associates the decorated class with a selector element that you use to insert it into HTML. In templates, directives typically appear within an element tag as attributes, either by name or as the target of an assignment or a binding.

## Structural directives

Structural directives are directives which change the DOM layout by adding and removing DOM elements.Structural directives alter layout by adding, removing, and replacing elements in the DOM. The example template uses two built-in structural directives to add application logic to how the view is rendered.

Angular provides a set of built-in structural directives (such as NgIf, NgForOf, NgSwitch and others) which are commonly used in all Angular projects

I a directive modifies the structure of template by removing or adding an element you use an aestrik.E.g *ngFor

- The [ngIf] directive - is used to conditionally display or hide elements based on a given expression. It adds or removes elements from the DOM based on the truthiness of the expression.
A structural directive that conditionally includes a template based on the value of an expression coerced to Boolean. When the expression evaluates to true, Angular renders the template provided in a then clause, and when false or null, Angular renders the template provided in an optional else clause. The default template for the else clause is blank.

When NgIf is false, Angular removes an element and its descendants from the DOM. Angular then disposes of their components, which frees up memory and resources.

```ts
import { CommonModule } from '@angular/common';
import { Component } from '@angular/core';

@Component({
  selector: 'app-direct',
  standalone: true,
  imports: [CommonModule],
  templateUrl: './direct.component.html',
  styleUrl: './direct.component.css'
})
export class DirectComponent {

  courses =[1]
}
```

```html
<div *ngIf="courses.length>0">
   List of courses
</div>
<div *ngIf="courses.length==0">
   No courses Yet
</div>
```

OR to avoid repeating ngIf use:-

```html
<div *ngIf="courses.length>0; else noCourses">
   List of courses
</div>
<ng-template #noCourses>
   No courses Yet
</ng-template>
```

Or use this approach for consistency:-

```html
<div *ngIf="courses.length>0; then Courses else noCourses">
</div>
<ng-template #Courses>
   List of courses
</ng-template>
<ng-template #noCourses>
   No courses Yet
</ng-template>
```

- The [ngFor] directive - The "ngFor" directive is used to iterate over a collection of items in Angular and generate the corresponding HTML elements for each item.
The "trackBy" function is used in conjunction with the ngFor directive in Angular to improve the performance of rendering lists. It provides away to uniquely identify and track items in the collection, allowing Angular to optimize the rendering process by reusing existing DOM elements instead of recreating them.

```ts
courses = ["course1","course2","course3"]
```

```html
<ul>
   <li *ngFor="let course of courses">{{ course }}</li>
</ul>
```

- The [ngSwitch] directive on a container specifies an expression to match against. The expressions to match are provided by ngSwitchCase directives on views within the container.

1. Every view that matches is rendered.
2. If there are no matches, a view with the ngSwitchDefault directive is rendered.
3. Elements within the [NgSwitch] statement but outside of any NgSwitchCase or ngSwitchDefault directive are preserved at the location.

## Attribute directives

Change the appearance or behavior of DOM elements and Angular components with attribute directives.Attribute directives alter the appearance or behavior of an existing element. In templates they look like regular HTML attributes, hence the name.

The ngModel directive, which implements two-way data binding, is an example of an attribute directive. ngModel modifies the behavior of an existing element (typically <input>) by setting its display value property and responding to change events.

The "ng-app" directive is used to define the root element of an AngularJS application.It initializes the application and auto-bootstraps the AngularJS framework.

The "ngStyle" directive is used to dynamically apply styles to an element based on the values of expressions in the component. It allows for dynamic styling without directly manipulating the CSS classes.

The "ngClass" directive is used to conditionally apply CSS classes to an element based on the values of expressions in the component. It allows for dynamic class
binding.

The "ngModel" directive is used for two-way data binding between a form input element and a component property. It allows the component to get and set the value
of the input element.

The "ngSwitch" directive is used to conditionally render content based on the value of an expression. It allows for multiple cases and provides an alternative to nested ngIf statements.

The "ng-container" directive is a structural directive that acts as a grouping element without rendering any additional element to the DOM. It is often used to apply
structural directives to multiple elements.

The "ng-content" directive is used to project content from a parent component into a child component. It allows for dynamic composition of components and flexible
content insertion.

The "RouterOutlet" directive is used in Angular to define the location where the router should render the components associated with different routes. It acts as a
placeholder for dynamically loaded components.

Angular'sng-template directive is used to define a template block that can be conditionally rendered or used as a template for other structural directives like ngIf
and ngFor. It allows for the creation of reusable templates that can be dynamically rendered or applied to elements. It is used by adding the ng-template directive to the template and providing it with a template block to be rendered or used as a template.

Angular's ng-container directive is a grouping element that does not generate any additional DOM element. It is used to apply structural directives to multiple elements without the need for a wrapping element. It is often used in conjunction with ngIf, ngFor, and ngTemplateOutlet to structure the layout and logic of the template.

Angular's ngTemplateOutlet directive is used to render a template dynamically within the current component's view. It allows the reuse of templates and the dynamic
insertion of content. It is used by adding the ngTemplateOutlet directive to an element and providing it with the template reference to be rendered.

Angular's ng-container directive is a grouping element that does not generate anyadditional DOM element. It is used to apply structural directives to multiple elements
without the need for a wrapping element. It is often used in conjunction with ngIf, ngFor, and ngTemplateOutlet to structure the layout and logic of the template.
