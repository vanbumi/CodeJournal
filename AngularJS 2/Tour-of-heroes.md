# Tour-of-heroes

Index:

<ul>
	<li><a href="#start">Start</a></li>
	<li><a href="#multi">Multiple Component</a></li>
</ul>

<h3 id="start">Start -  Show our Hero</h3>

display Hero data in our app

add two properties to our AppComponent, a title property for the application name and a hero property for a hero named "Windstorm".

	export class AppComponent {
	  title = 'Tour of Heroes';
	  hero = 'Windstorm';
	}


<h3 id="multi">Multiple Component</h3>

> **Naming conventions**
We like to identify at a glance which classes are components and which files contain components.
Notice that we have an **AppComponent** in a file named **app.component.ts** and our new **HeroDetailComponent** is in a file named **hero-detail.component.ts**.
All of our component names end in **"Component"**. All of our component file names end in **".component"**.
We spell our file names in lower dash case (AKA kebab-case) so we don't worry about case sensitivity on the server or in source control.

hero-detail.component.ts

	import { Component, Input } from '@angular/core';

	@Component({
		selector: 'my-hero-detail',

		template:`
		<div *ngIf='hero'>	
		  <h2>{{hero.name}} details!</h2>
		  <div><label>id: </label>{{hero.id}}</div>
		  <div>
		  	<label>Name: </label>
		  	<input [(ngModel)]="hero.name" placeholder='name'>
		  </div>
		</div>
		` 
	})

	export class HeroDetailComponent {

	} 

**Descriptions**

We begin by importing the Component and Input decorators from Angular because we're going to need them soon.

We create metadata with the @Component decorator where we specify the selector name that identifies this component's element. Then we export the class to make it available to other components.

When we finish here, we'll import it into AppComponent and create a corresponding **&lt;my-hero-detail&gt;** element.

**Relocating the Hero class from app.component.ts to its own hero.ts file**.