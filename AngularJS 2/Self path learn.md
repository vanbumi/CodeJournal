**Self Learning**
# Angular 2

Index

<ul>
	<li><a href="#arsitektur">ARCHITECTURE OVERVIEW</a></li>
	<li><a href="#display">DISPLAYING DATA</a></li>
</ul>

## Learning Path

You don't have to read the guide straight through. Most pages stand on their own.

For those **new to Angular**, the recommended learning path **runs through** the **Basics section**:

1. For the **big picture**, read the **Architecture overview**.

2. Try **QuickStart**. QuickStart is the "Hello, World" of Angular 2. It shows you how to set up the libraries and tools you'll need to write any Angular app.

3. Take the Tour of Heroes **tutorial**, which picks up where QuickStart leaves off, and builds a simple data-driven app. The app demonstrates the essential characteristics of a professional application: a sensible project structure, data binding, master/detail, services, dependency injection, navigation, and remote data access.

4. **Displaying Data** explains how to display information on the screen.

5. **User Input** covers how Angular responds to user behavior.

6. **Forms** handles user data entry and validation within the UI.

7. **Dependency Injection** is the way to build large, maintainable applications from small, single-purpose parts.

**Template Syntax** is a comprehensive study of Angular template HTML.

After reading the above sections, you can skip to any other pages on this site.

---

<h2 id="arsitektur">ARCHITECTURE OVERVIEW</h2> 

**The basic building blocks of Angular 2 applications**

Angular 2 is a framework for building client applications in HTML and either JavaScript or a language (like Dart or TypeScript) that compiles to JavaScript.

The framework consists of several libraries, some of them core and some optional.

You write Angular applications by composing HTML templates with Angularized markup, **writing component classes** to manage those **templates**, adding application logic in **services**, and boxing components and services in **modules**.

Then you launch the app by **bootstrapping** the **root module**. Angular takes over, presenting your application content in a browser and responding to user interactions according to the instructions you've provided.

Of course, there is more to it than this. You'll learn the details in the pages that follow. For now, focus on the big picture.

![ng2-architecture](http://res.cloudinary.com/medio/image/upload/v1473669443/overview2_bddgm5.png)

**The architecture diagram identifies the eight main building blocks of an Angular 2 application:**

1. [Modules](https://angular.io/docs/ts/latest/guide/architecture.html#!#modules) <a href="#modules">| Read</a> 
2. [Component](https://angular.io/docs/ts/latest/guide/architecture.html#!#components) <a href="#component">| Read</a>
3. [Templates](https://angular.io/docs/ts/latest/guide/architecture.html#!#templates) <a href="#templates">| Read</a>
4. [Metadata](https://angular.io/docs/ts/latest/guide/architecture.html#!#metadata) <a href="#metadata">| Read</a>
5. [Data Binding](https://angular.io/docs/ts/latest/guide/architecture.html#!#data-binding) <a href="#databinding">| Read</a>
6. [Directive](https://angular.io/docs/ts/latest/guide/architecture.html#!#directives) <a href="#directive">| Read</a>
7. [Services](https://angular.io/docs/ts/latest/guide/architecture.html#!#services) <a href="#services">| Read</a>
8. [Dependency Injection](https://angular.io/docs/ts/latest/guide/architecture.html#!#dependency-injection) <a href="#dependency">| Read</a>

<h3 id="modules">Modules</h3>

Angular apps are modular and Angular has its own modularity system called Angular modules or **NgModules**.

**Angular modules are a big deal**. This page introduces modules; the Angular modules page covers them in depth.

Every Angular app has **at least one module**, the root module, conventionally named **AppModule**.

While the **root module** may be the only module in a small application, most apps have many more feature modules, each a cohesive (terpadu) block of code dedicated to an application domain, a workflow, or a closely related set of capabilities.

An **Angular module**, whether a **root** or **feature**, **is a class with an @NgModule** decorator.

> **Decorators** are functions that modify JavaScript classes. Angular has many decorators that attach metadata to classes so that it knows what those classes mean and how they should work. Learn more about decorators on the web.

**NgModule** is a decorator function that **takes a single metadata object** whose properties describe the module. The most important properties are:

+ **declarations** - the view classes that belong to this module. Angular has three kinds of view classes: **components**, **directives**, and **pipes**.

+ **exports** - the subset of declarations that should be visible and usable in the component templates of other modules.

+ **imports** - other modules whose exported classes are needed by component templates declared in this module.

+ **providers** - creators of services that this module contributes to the global collection of services; they become accessible in all parts of the app.

+ **bootstrap** - the main application view, called the root component, that hosts all other app views. Only the root module should set this bootstrap property.

Here's a simple root module:

app/app.module.ts

	import { NgModule }      from '@angular/core';
	import { BrowserModule } from '@angular/platform-browser';
	@NgModule({
	  imports:      [ BrowserModule ],
	  providers:    [ Logger ],
	  declarations: [ AppComponent ],
	  exports:      [ AppComponent ],
	  bootstrap:    [ AppComponent ]
	})
	export class AppModule { }

> The export of AppComponent is just to show how to export; it isn't actually necessary in this example. A root module has no reason to export anything because other components don't need to import the root module.

Launch an application by bootstrapping its root module. During development you're likely to bootstrap the AppModule in a main.ts file like this one.

app/main.ts

	import { platformBrowserDynamic } from '@angular/platform-browser-dynamic';
	import { AppModule } from './app.module';

	platformBrowserDynamic().bootstrapModule(AppModule);

**Angular modules vs. JavaScript modules**

The Angular module — a class decorated with **@NgModule** — is a **fundamental feature of Angular**.

*JavaScript also has its own module system for managing collections of JavaScript objects. It's completely different and unrelated to the Angular module system*.

In JavaScript each file is a module and all objects defined in the file belong to that module. The module declares some objects to be public by marking them with the export key word. Other JavaScript modules use import statements to access public objects from other modules.

	import { NgModule }     from '@angular/core';
	import { AppComponent } from './app.component';

	export class AppModule { }

> [Learn more about the JavaScript module system on the web.](http://exploringjs.com/es6/ch_modules.html)

**Angular libraries**

Angular ships as a collection of **JavaScript modules**. You can think of them as **library modules++.

Each Angular library name begins with the **@angular** prefix.

**You install them with the npm package manager and import parts of them with JavaScript import statements**.

For example, import Angular's Component decorator from the @angular/core library like this:

	import { Component } from '@angular/core';

You also import Angular modules from Angular libraries using JavaScript import statements:

	import { BrowserModule } from '@angular/platform-browser';

In the example of the simple root module above, the application module needs material from within that BrowserModule. To access that material, add it to the @NgModule metadata imports like this.

	imports: [ BrowserModule ],

In this way you're using both the Angular and JavaScript module systems together.

It's easy to confuse the two systems because they share the common vocabulary of "imports" and "exports". Hang in there. **The confusion yields to clarity with time and experience**.

> Learn more from the [Angular modules](https://angular.io/docs/ts/latest/guide/ngmodule.html) page.

<h3 id="component">Component</h3>

A **component** controls a patch (potongan/bagian) of screen called a view.

For example, the following views are controlled by components:

+ The app root with the navigation links.
+ The list of heroes.
+ The hero editor.

You define a component's application logic—what it does to support the view—inside a class. The class interacts with the view through an API of properties and methods.

For example, this **HeroListComponent** has a heroes property that returns an array of heroes that it acquires (didapatkan) from a service. HeroListComponent also has a **selectHero() method** that sets a **selectedHero** property when the user clicks to choose a hero from that list.

app/hero-list.component.ts (class)

	export class HeroListComponent implements OnInit {
	  heroes: Hero[];
	  selectedHero: Hero;

	  constructor(private service: HeroService) { }

	  ngOnInit() {
	    this.heroes = this.service.getHeroes();
	  }

	  selectHero(hero: Hero) { this.selectedHero = hero; }
	}

Angular creates, updates, and destroys components as the user moves through the application. Your app can take action at each moment in this lifecycle through optional lifecycle hooks, like ngOnInit() declared above.

<h3 id="templates">Templates</h3>

You define a component's view with its companion **template**. **A template is a form of HTML that tells Angular how to render the component**.

A template looks like regular HTML, except for a few differences. Here is a template for our HeroListComponent:

app/hero-list.component.html

	<h2>Hero List</h2>
	<p><i>Pick a hero from the list</i></p>
	<ul>
	  <li *ngFor="let hero of heroes" (click)="selectHero(hero)">
	    {{hero.name}}
	  </li>
	</ul>

	<hero-detail *ngIf="selectedHero" [hero]="selectedHero"></hero-detail>

Although this template uses typical HTML elements like **&lt;h2&gt;** and **&lt;p&gt;**, it also has some differences. Code like ** *ngFor **, **{{hero.name}}**, **(click)**, **[hero]**, and **&lt;hero-detail&gt;** uses Angular's template syntax.

In the last line of the template, the &lt;hero-detail&gt; tag is a custom **element** that represents a new component, **HeroDetailComponent**.

The **HeroDetailComponent** is a different component than the **HeroListComponent** you've been reviewing. The **HeroDetailComponent** (code not shown) presents facts about a particular hero, the hero that the **user selects** from the list presented by the **HeroListComponent**. The **HeroDetailComponent** is a **child** of the **HeroListComponent**.

Notice how &lt;hero-detail&gt; rests comfortably among native HTML elements. Custom components mix seamlessly with native HTML in the same layouts.

<h3 id="metadata">Metadata</h3>

> Metadata tells Angular how to process a class.

Looking back at the code for HeroListComponent, you can see that it's just a class. There is no evidence of a framework, no "Angular" in it at all.

In fact, HeroListComponent really is just a class. It's not a component until you tell Angular about it.

To tell Angular that HeroListComponent is a component, **attach metadata to the class**.

In TypeScript, you attach metadata by using a decorator. Here's some metadata for HeroListComponent:

app/hero-list.component.ts (metadata)

	@Component({
	  selector:    'hero-list',
	  templateUrl: 'app/hero-list.component.html',
	  providers:   [ HeroService ]
	})

	export class HeroListComponent implements OnInit {

	/* . . . */

	}

Here is the **@Component decorator**, which **identifies** the class immediately below it as a component class.

The **@Component** decorator takes a required configuration object with the information Angular needs to create and present the **component and its view**.

Here are a few of the possible @Component configuration options:

+ **selector**: **CSS selector** that tells Angular to create and insert an instance of this component where it finds a &lt;hero-list&gt; tag in parent HTML. For example, if an app's HTML contains &lt;hero-list&gt;&lt;/hero-list&gt;, then Angular inserts an instance of the HeroListComponent view between those tags.

+ **templateUrl**: address of this component's HTML template, shown above.

+ **directives**: array of the components or directives that this template requires. In the last line of hero-list.component.html, Angular inserts a HeroDetailComponent in the space indicated by <hero-detail> tags. Angular does so only if HeroDetailComponent is in this directives array.

+ **providers**: array of **dependency injection** providers for services that the component requires. This is one way to tell Angular that the component's constructor requires a **HeroService** *so it can get the list of heroes to display*.

**The metadata** in the **@Component** tells Angular **where to get the major building blocks you specify for the component**.

**The template**, **metadata**, and **component** together describe a **view**.

Apply other metadata decorators in a similar fashion to guide Angular behavior. **@Injectable**, **@Input**, and **@Output** are a few of the more popular decorators.

The architectural takeaway is that you must add metadata to your code so that Angular knows what to do.

<h3 id="databinding">Data Binding</h3>

Without a framework, you would be responsible for pushing data values into the HTML controls and turning user responses into actions and value updates. Writing such push/pull logic by hand is tedious (membosankan), error-prone, and a nightmare to read as any experienced **jQuery programmer** can attest (membuktikan).

**Angular supports data binding**, a mechanism for coordinating **parts of a template** with **parts of a component**. Add binding markup to the template HTML to tell Angular how to connect both sides.

![databinding](http://res.cloudinary.com/medio/image/upload/v1473689199/databinding_aphb4d.png)

As the diagram shows, there are four forms of data binding syntax. Each form has a direction — to the DOM, from the DOM, or in both directions.


The HeroListComponent example template has three forms:

app/hero-list.component.html (binding)

	<li>{{hero.name}}</li>
	<hero-detail [hero]="selectedHero"></hero-detail>
	<li (click)="selectHero(hero)"></li>

+ The **{{hero.name}} interpolation** displays the **component's hero.name** property value within the <li> tags.

+ The **[hero] property binding** passes the value of **selectedHero** from the parent HeroListComponent to the hero property of the child **HeroDetailComponent**.

+ The (click) event binding **calls** the component's **selectHero** method when the user clicks a hero's name.

Two-way data binding is an important **fourth form** that combines **property and event binding** in a single notation, using the **ngModel** directive. Here's an example from the HeroDetailComponent template:

app/hero-detail.component.html (ngModel)

	<input [(ngModel)]="hero.name">

In **two-way binding**, a **data property value** flows to the input box from the component as with property binding. The user's changes also flow back to the component, resetting the property to the latest value, as with event binding.

Angular processes all data bindings once per JavaScript event cycle, **from the root of the application component tree through all child components**.

![component databinding](http://res.cloudinary.com/medio/image/upload/v1473690346/component-databinding_my2wpg.png)

Data binding plays an important role in communication between a template and its component.

![parent child binding](http://res.cloudinary.com/medio/image/upload/v1473690459/parent-child-binding_yy12pg.png)

Data binding is also important for communication between parent and child components.

<h3 id="directive">Directive</h3>

![meta directive](http://res.cloudinary.com/medio/image/upload/v1473691624/metadirective_lxhkur.png)

Angular templates are dynamic. When Angular renders them, it transforms the DOM according to the instructions **given by directives**.

**A directive is a class with directive metadata**. In TypeScript, apply the **@Directive** decorator **to attach metadata to the class**.

**A component is a directive-with-a-template**; a **@Component** decorator is actually a **@Directive** decorator extended with template-oriented features.

> While a component is technically a directive, components are so distinctive and central to Angular applications that this architectural overview separates components from directives.

Two other kinds of directives exist: structural and attribute directives.

They tend to appear within an element tag as attributes do, sometimes by name but more often as the target of an assignment or a binding.

**Structural directives** alter layout by adding, removing, and replacing elements in DOM.

The example template uses two built-in structural directives:

app/hero-list.component.html (structural)

	<li *ngFor="let hero of heroes"></li>
	<hero-detail *ngIf="selectedHero"></hero-detail>

+ ** *ngFor ** tells Angular to stamp out one &lt;li&gt; per hero in the heroes list. (Loops).
+ ** *ngIf ** includes the HeroDetail component only if a selected hero exists. (If Condition).

**Attribute** directives alter the appearance or behavior of an existing element. In templates they look like regular HTML attributes, hence the name.

The **ngModel** directive, which **implements two-way data binding**, is an example of an attribute directive. **ngModel** modifies the behavior of an existing element (typically an &lt;input&gt;) by setting its display **value** property and responding to **change** events.

app/hero-detail.component.html (ngModel)

	<input [(ngModel)]="hero.name">

Angular has a few more directives that either alter the layout structure (for example, ngSwitch) or modify aspects of DOM elements and components (for example, **ngStyle** and **ngClass**).

Of course, you can also write your own directives. Components such as HeroListComponent are one kind of custom directive.

<h3 id="services">Services</h3>

Service is a **broad category encompassing any value** (kategori yang luas meliputi nilai apapun), function, or feature that your application needs.

Almost anything can be a service. A service is typically a class with a narrow, well-defined purpose. It should do something specific and do it well.

Examples include:

+ logging service
+ data service
+ message bus
+ tax calculator
+ application configuration

There is nothing specifically Angular about services. Angular has no definition of a service. There is no service base class, and no place to register a service.

Yet services are fundamental to any Angular application. Components are big consumers of services.

Here's an example of a service class that logs to the browser console:

app/logger.service.ts (class)

	export class Logger {
	  log(msg: any)   { console.log(msg); }
	  error(msg: any) { console.error(msg); }
	  warn(msg: any)  { console.warn(msg); }
	}

Here's a HeroService that fetches heroes and returns them in a resolved Promise. The HeroService depends on the Logger service and another BackendService that handles the server communication grunt work.

app/hero.service.ts (class)

	export class HeroService {
	  private heroes: Hero[] = [];

	  constructor(
	    private backend: BackendService,
	    private logger: Logger) { }

	  getHeroes() {
	    this.backend.getAll(Hero).then( (heroes: Hero[]) => {
	      this.logger.log(`Fetched ${heroes.length} heroes.`);
	      this.heroes.push(...heroes); // fill cache
	    });
	    return this.heroes;
	  }
	}

**Services are everywhere**.

Component classes should be lean (ramping). They don't fetch data from the server, validate user input, or log directly to the console. **They delegate such tasks to services**.

A component's job is **to enable the user experience and nothing more**. It mediates between the view (rendered by the template) and the application logic (which often includes some notion of a model). A good component presents properties and methods for data binding. It delegates everything nontrivial (tidak sepele) to services.

Angular doesn't enforce these principles. It won't complain if you write a "kitchen sink" component with 3000 lines.

Angular does help you follow these principles by making it easy to factor your application logic into services and make those services available to components through dependency injection.

<h3 id="dependency">Dependency injection</h3>

**Dependency injection** *is a way to supply a new instance of a class with the fully-formed dependencies it requires*. Most dependencies are services. Angular uses dependency injection **to provide new components with the services they need**.

Angular can tell which services a component needs by looking at the types of its constructor parameters. For example, the constructor of your HeroListComponent needs a HeroService:

app/hero-list.component.ts (constructor)

	constructor(private service: HeroService) { }

When Angular creates a component, it first asks an injector for the services that the component requires.

An injector maintains a container of service instances that it has previously created. If a requested service instance is not in the container, the injector makes one and adds it to the container before returning the service to Angular. When all requested services have been resolved and returned, Angular can call the component's constructor with those services as arguments. This is dependency injection.

The process of HeroService injection looks a bit like this:

![Injector](http://res.cloudinary.com/medio/image/upload/v1473697120/injector-injects_gngunr.png)	
If the injector doesn't have a HeroService, how does it know how to make one?

In brief, you must have previously registered a provider of the HeroService with the injector. A provider is something that can create or return a service, typically the service class itself.

You can register providers in modules or in components.

In general, add providers to the root module so that the same instance of a service is available everywhere.

app/app.module.ts (module providers)

	providers: [
	  BackendService,
	  HeroService,
	  Logger
	],

Alternatively, register at a component level in the providers property of the @Component metadata:

app/hero-list.component.ts (component providers)

	@Component({
	  selector:    'hero-list',
	  templateUrl: 'app/hero-list.component.html',
	  providers:   [ HeroService ]
	})

Registering at a component level means you get a new instance of the service with each new instance of that component.

Points to remember about dependency injection:

Dependency injection is wired into the Angular framework and used everywhere.

The injector is the main mechanism.

An injector maintains a container of service instances that it created.
An injector can create a new service instance from a provider.
A provider is a recipe for creating a service.

Register providers with injectors.

---

Wrap up

You've learned the basics about the eight main building blocks of an Angular application:

Modules
Components
Templates
Metadata
Data binding
Directives
Services
Dependency injection
That's a foundation for everything else in an Angular application, and it's more than enough to get going. But it doesn't include everything you need to know.

Here is a brief, alphabetical list of other important Angular features and services. Most of them are covered in this documentation (or soon will be).

Animations: Animate component behavior without deep knowledge of animation techniques or CSS with Angular's animation library.

Change detection: The change detection documentation will cover how Angular decides that a component property value has changed, when to update the screen, and how it uses zones to intercept asynchronous activity and run its change detection strategies.

Events: The events documentation will cover how to use components and services to raise events with mechanisms for publishing and subscribing to events.

Forms: Support complex data entry scenarios with HTML-based validation and dirty checking.

HTTP: Communicate with a server to get data, save data, and invoke server-side actions with an HTTP client.

Lifecycle hooks: Tap into key moments in the lifetime of a component, from its creation to its destruction, by implementing the lifecycle hook interfaces.

Pipes: Use pipes in your templates to improve the user experience by transforming values for display. Consider this currency pipe expression:


price | currency:'USD':true
It displays a price of "42.33" as $42.33.

Router: Navigate from page to page within the client application and never leave the browser.

Testing: Run unit tests with Angular's testing library on your application parts as they interact with the Angular framework.

---

<h2 id="display">DISPLAYING DATA</h2>

Interpolation and other forms of property binding help us show app data in the UI.

We typically display data in Angular by **binding controls** in an HTML template to properties of an Angular component.

In this chapter, we'll create a component with a list of heroes. Each hero has a name. We'll display the list of hero names and conditionally show a message below the list.

The final UI looks like this:

![list hero](http://res.cloudinary.com/medio/image/upload/v1473828102/final_aj0qar.png)

### Showing component properties with interpolation

The easiest way to display a component property is to bind the property name through interpolation. With interpolation, we put the property name in the view template, enclosed in double curly braces: {{myHero}}.

Let's build a small illustrative example together.

Create a new project folder (displaying-data) and follow the steps in the QuickStart.

Then modify the app.component.ts file by changing the template and the body of the component. When we're done, it should look like this:

.....................
.....................

<h3>Template inline or template file?</h3>

We can store our component's template in one of two places. 

+ inline using the template property, as we do here. 
+ separate HTML file and link to it in the component metadata using the @Component decorator's **templateUrl** property.

The choice between **inline** and **separate HTML** is a matter of taste, circumstances, and organization policy. Here we're using inline HTML because the template is small, and the demo is simpler without the additional HTML file.

In either style, the template data bindings have the same access to the component's properties.

<h3>Constructor or variable initialization?</h3>

We initialized our component properties using variable assignment. This is a wonderfully concise (*ringkas*) and compact technique.

Some folks prefer to declare the properties and initialize them within a constructor like this:

	export class AppCtorComponent {
	  title: string;
	  myHero: string;

	  constructor() {
	    this.title = 'Tour of Heroes';
	    this.myHero = 'Windstorm';
	  }
	}

That's fine too. The choice is a matter of taste and organization policy. We'll adopt the more terse "variable assignment" style in this chapter simply because there will be less code to read.

<h3>Showing an array property with *ngFor</h3>

We want to display a list of heroes. We begin by adding an *array of hero names* to the component and redefine myHero to be the first name in the array.

app/app.component.ts (template)

	  template: `
	    <h1>{{title}}</h1>
	    <h2>My favorite hero is: {{myHero}}</h2>
	    <p>Heroes:</p>
	    <ul>
	      <li *ngFor="let hero of heroes">
	        {{ hero }}
	      </li>
	    </ul>
	  `

Our presentation is the familiar HTML unordered list with <ul> and <li> tags. Let's focus on the <li> tag.

	<li *ngFor="let hero of heroes">
	  {{ hero }}
	</li>

We added a somewhat mysterious *ngFor to the <li> element. That's the Angular "repeater" directive. Its presence on the <li> tag marks that <li> element (and its children) as the "repeater template".

Notice the hero in the ngFor double-quoted instruction; it is an example of a template input variable.

Angular duplicates the &lt;li&gt; for each item in the list, setting the **hero variable** to the item (the hero) in the current iteration (*perulangan*). Angular uses that variable as the context for the interpolation in the double curly braces.

<h3>Creating a class for the data</h3>

We are defining our data directly inside our component. *That's fine for a demo but certainly isn't a best practice*. It's not even a good practice. Although we won't do anything about that in this chapter, we'll make a mental note to fix this down the road.

At the moment, we're binding to an array of strings. We do that occasionally in real applications, but most of the time we're binding to more specialized **objects**.

Let's turn our array of hero names into an **array** of **Hero objects**. For that we'll need a **Hero class**.

Create a new file in the app folder called hero.ts with the following code:




---



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

[Display Data](https://angular.io/docs/ts/latest/guide/displaying-data.html)

Display data in Angular is by binding controls in an HTML template to properties of an Angular component.

In this chapter, we'll create a component with a list of heroes. Each hero has a name. We'll display the list of hero names and conditionally show a message below the list.

The final UI looks like this:




