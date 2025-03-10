# Component

The application source code resides inside the src\app folder, in the root of our Angular
CLI project. It contains all the files needed to build and test our Angular application,
including a component and a module. The component is the main component of the Angular application:

```ts
import { Component } from '@angular/core';
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.css']
})
export class AppComponent {
  title = 'my-angular';
}
```

A component in Angular is a reusable building block that encapsulates the template,logic, and styling required to render a part of the user interface.

Components are the main building blocks for Angular applications. Each component consists of:

1. An HTML template that declares what renders on the page
2. A TypeScript class that defines behavior
3. A CSS selector that defines how the component is used in a template
4. Optionally, CSS styles applied to the template

The following properties characterize an Angular component:
• `selector`: A unique name that is used to identify and declare the component inside HTML content. It is used as an HTML tag, just like any native HTML element, such as <app-root></app-root>.

NOTE:- The Angular CLI provides the app prefix by default in component selectors.We can use a custom one using the --prefix option when creating a new Angular CLI application from scratch. A custom prefix can be based on the name of an organization or a particular product, and it helps avoid collisions with other libraries or modules.

• `templateUrl`: The path pointing to an HTML file that contains the HTML
content of the component, which is called the template of the component.
• `styleUrls`: A list of paths where each one points to a stylesheet file containing the
CSS styles of the component.

The preceding properties are defined using the `@Component decorator`. It is a function
that decorates the TypeScript class of the component and recognizes it as an Angular
component.

## Creating a Component

There are two ways of creating a component:

1. The best way to create a component is with the Angular CLI.
2. You can also create a component manually.

### To create a component using the Angular CLI

- From a terminal window, navigate to the directory containing your application.
- Run the **ng generate component component-name** command, where component-name is the name of your new component.

By default, this command creates the following:

 1. A directory named after the component
 2. A component file, component-name.component.ts
 3. A template file, component-name.component.html
 4. A CSS file, component-name.component.css
 5. A testing specification file, component-name.component.spec.ts

### Creating a component manually

- Navigate to your Angular project directory.
- Create a new file, component-name.component.ts.
- At the top of the file, add the following import statement.

```ts
  import { Component } from '@angular/core';
```

- After the import statement, add a @Component decorator.

```ts
@Component({
})
```

- Choose a CSS selector for the component.

```ts
@Component({
  selector: 'app-component-overview',
})
```

- Define the HTML template that the component uses to display information. In most cases, this template is a separate HTML file.

```ts
@Component({
  selector: 'app-component-overview',
  templateUrl: './component-overview.component.html',
})
```

- Select the styles for the component's template. In most cases, you define the styles for your component's template in a separate file.

```ts
@Component({
  selector: 'app-component-overview',
  templateUrl: './component-overview.component.html',
  styleUrls: ['./component-overview.component.css']
})
```

- Add a class statement that includes the code for the component.

```ts
export class ComponentOverviewComponent {

}
```

## Steps when using components

1. Create a component.
2. Register component in the module.
3. Add an element in an HTML markup.

- Creating a Component

```ts

import {Component} from '@angular/core'

@Component({
   selector:'courses',
   template:'<h2>Courses</h2>'
})
export class CourseComponent{

}
```

- Register component in the module:

```ts
import { BrowserModule } from '@angular/platform-browser'
import { NgModule } from '@angular/core'
import { CourseComponent } from './courses.component'

@NgModule({
   declarations: [
      AppComponent,
      CourseComponent
   ],
   imports: [
      BrowserModule
   ],
   providers: [],
   bootstrap: [AppComponent]
})
export class AppModule{}
```

```ts
@Component({
  selector: 'app-root',
  standalone: true,
  imports: [
   CourseComponent
 
  ],
  templateUrl: './app.component.html',
  styleUrl: './app.component.css'
})
export class AppComponent {
  title = 'collo';
}
```

- adding element in an HTML markup:

```html
<courses></courses>
```

## Accepting data with input properties

When you use a component, you commonly want to pass some data to it. A component specifies the data that it accepts by declaring inputs:

- Declaring inputs with the @Input decorator:-You can alternatively declare component inputs by adding the @Input decorator to a property:

```ts
@Component({...})
export class CustomSlider {
  @Input() value = 0;
}
```

Binding to an input is the same in both signal-based and decorator-based inputs:

```ts
<custom-slider [value]="50" />
```

Customizing decorator-based inputs - The @Input decorator accepts a config object that lets you change the way that input works.

```ts
@Component({...})
export class CustomSlider {
  @Input({required: true}) value = 0;
}
```

If you try to use a component without specifying all of its required inputs, Angular reports an error at build-time.
