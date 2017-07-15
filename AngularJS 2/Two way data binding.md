## To create two way databinding in input form

Steps:

1. In app.module.ts
	import { FormsModule }   from '@angular/forms';

2. Add FormsModule in decoration NgModule:

	@NgModule({
	  imports:      [ 
	  BrowserModule 
	  FormsModule

3. template: `

		<h1>{{title}}</h1>
		<h2>{{hero.name}} details!</h2>
	  	<div><label>id: </label>{{hero.id}}</div>
		  <div>
		  	<label>Name: </label>
		  	<input [(ngModel)]="hero.name" placeholder='name'>
		  </div>

	  `