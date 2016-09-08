### Self path learning
# Angular 2

**The architecture diagram identifies the eight main building blocks of an Angular 2 application:**

1 [Modules](https://angular.io/docs/ts/latest/guide/architecture.html#!#modules)
2 [Component](https://angular.io/docs/ts/latest/guide/architecture.html#!#components)
3 [Templates](https://angular.io/docs/ts/latest/guide/architecture.html#!#templates)
4 [Metadata](https://angular.io/docs/ts/latest/guide/architecture.html#!#metadata)
5 [Data Binding](https://angular.io/docs/ts/latest/guide/architecture.html#!#data-binding)
6 [Directive](https://angular.io/docs/ts/latest/guide/architecture.html#!#directives)
7 [Services](https://angular.io/docs/ts/latest/guide/architecture.html#!#services)
8 [Dependency Injection](https://angular.io/docs/ts/latest/guide/architecture.html#!#dependency-injection)

**Other important Angular features and services**

+ **Animations**: Animate component behavior without deep knowledge of animation techniques or CSS with Angular's animation library.

+ **Change detection**: The change detection documentation will cover how Angular decides that a component property value has changed, when to update the screen, and how it uses zones to intercept asynchronous activity and run its change detection strategies.

+ **Events**: The events documentation will cover how to use components and services to raise events with mechanisms for publishing and subscribing to events.

+ **Forms**: Support complex data entry scenarios with HTML-based validation and dirty checking.

+ **HTTP**: Communicate with a server to get data, save data, and invoke server-side actions with an HTTP client.

+ **Lifecycle hooks**: Tap into key moments in the lifetime of a component, from its creation to its destruction, by implementing the lifecycle hook interfaces.

+ **Pipes**: Use pipes in your templates to improve the user experience by transforming values for display. Consider this currency pipe expression:

	price | currency:'USD':true

It displays a price of "42.33" as $42.33.

+ **Router**: Navigate from page to page within the client application and never leave the browser.

+ **Testing**: Run unit tests with Angular's testing library on your application parts as they interact with the Angular framework.

**DISPLAYING DATA**

[How to Display Data in Angular 2](https://angular.io/docs/ts/latest/guide/displaying-data.html)

## Two-way data binding with ngModel

