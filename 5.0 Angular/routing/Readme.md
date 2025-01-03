# Routing

Routing in Angular allows the users to create a single-page application with multiple views and navigation between them. Users can switch between these views without losing the application state and properties.

@angular/router Implements the Angular Router service , which enables navigation from one view to the next as users perform application tasks.

Angular Router is a built-in module in Angular that provides navigation and routing functionality. It allows developers to create single-page applications with multiple views and handle navigation between them.

Defines the Route object that maps a URL path to a component, and the RouterOutlet directive that you use to place a routed view in a template, as well as a complete API for configuring, querying, and controlling the router state.Import RouterModule to use the Router service in your app.

Angular's Router is a module that provides a way to implement navigation and routing in an Angular application. It allows for defining routes, navigating between
routes, and handling route parameters and query parameters. The Router module is used by importing the RouterModule in the application's module and configuring the
routes using the RouterModule.forRoot() method. The Router module is then used by injecting the Router service into components and using its methods to navigate and
interact with therouting system.

## Configuration

## Router outlets

The router-outlet is a directive that's available from the @angular/router package and is used by the router to mark where in a template, a matched component should be inserted.

Thanks to the router outlet, your app will have multiple views/pages and the app template acts like a shell of your application. Any element, you add to the shell will be rendered in each view, only the part marked by the router outlet will be changed between views.

## Router links

In Angular, routerLink when applied to an element in a template, makes that element a link that initiates navigation to a route. Navigation opens one or more routed components in one or more `<router-outlet>` locations on the page.

## Router Events

The Angular Router raises events when it navigates from one route to another route. It raises several events such as `NavigationStart`, `NavigationEnd`, `NavigationCancel`, `NavigationError`, `ResolveStart`, etc. You can listen to these events and find out when the state of the route changes. Some of the useful events are route change start (NavigationStart) and route change end (NavigationEnd).

## Route Guards

Angular route guards are interfaces provided by Angular which, when implemented, allow us to control the accessibility of a route based on conditions provided in class implementation of that interface.

Some types of angular guards are `CanActivate`, `CanActivateChild`, `CanLoad`, `CanDeactivate` and `Resolve`.

## Lazy loading

Lazy loading is a technique in Angular that allows you to load JavaScript components asynchronously when a specific route is activated. It improves the application load time speed by splitting the application into several bundles. The bundles are loaded as required when the user navigates through the app.

## Angular's ActivatedRoute and how is it used

Angular's ActivatedRoute is a service that provides information about the currently activated route. It contains route parameters, query parameters, data resolved for the route, and other route-related information. It is used by injecting the ActivatedRoute service into a component and accessing its properties and methods to retrieve information about the current route
