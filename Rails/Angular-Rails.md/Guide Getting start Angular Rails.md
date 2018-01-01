Getting Started with Angular and Rails

Whenever I teach myself a new technology, I like to teach myself by building a real program using that technology. And when I build that program, I usually do it in to steps:

Build a "spike" where I don't worry about testing or even good code too much
Start over and do it again, more carefully this time
This guide will cover that first step, the spike. That should be enough to get you started. If you want more help after that, I'll tell you where you can find it when we're done.

For this particular application we're going to take three steps:

Create a Rails app
Create an Angular app
Get the two to talk to each other
Creating the Rails app

First, make sure you have Rails 5 installed.

  $ rails new home_library --api -T -d postgresql
  $ cd home_library

Quick rundown of the flags:

--api: We want to create an API-only app. This, as you may know, is a new feature of Rails 5.
-T: We don't want to use Test::Unit. (We'll use RSpec.)
-d postgresql: We want to use PostgreSQL.
After that command finishes running, create the database and start the server.

  $ rails db:create
  $ rails server --binding 0.0.0.0

Don't forget to initialize your Git repo before moving on.

  $ git init
  $ git add .
  $ git commit -m "Initial commit."

Creating the Angular app

We're going to use Angular CLI to create our Angular app. It can be installed using the following command. If you don't have NPM installed on your machine, you'll need to install it.

  $ npm install -g angular-cli

The Angular CLI executable is called ng. Run ng -v to verify that Angular CLI has been installed.

  $ ng -v

As of this writing the latest version of Angular CLI is 1.0.0-beta.16.

We'll now create a new Angular app with the same name as the Rails app.

  $ ng new home-library

What we have right now is a slightly silly situation. Our Rails application lives at /home_library. The Angular application lives at the repetitively-named /home_library/home-library. When I have an Angular application nested within a Rails application, I always call its directory client, which is a name I've just arbitrarily chosen because I think it makes sense. Let's rename our Angular directory now, and then cd into it.

  $ mv home-library client
  $ cd client

Lastly, run npm start to spin up the front-end server.

  $ npm start

If you go now to http://localhost:4200/, you should see a page that says "app works!".

Getting Angular and Rails to talk to each other

Step 1: Add a resource to Rails

Let's cd back into the Rails directory:

$ cd ..
Now we'll generate our resource and run the migrations so our database table gets created.

  $ rails generate scaffold book name:string
  $ rails db:migrate

When I'm building single-page applications, I like to namespace my routes under /api. (Sometimes you'll want /api/v1, /api/v2, etc., but in this case we'll just do /api.)

# config/routes.rb

  Rails.application.routes.draw do
    scope '/api' do
      resources :books
    end
  end

Then, so we have some actual data to work with, let's add some seed data.

# db/seeds.rb

  Book.create!([
    { name: 'Copying and Pasting from Stack Overflow' },
    { name: 'Trying Stuff Until it Works' }
  ])

Run rails db:seed to insert that data into the database.

  $ rails db:seed

Now, if you visit http://localhost:3000/api/books.json, you should see the following:

  [{
    "id": 1,
    "name": "Copying and Pasting from Stack Overflow",
    "created_at": "2016-09-29T12:31:26.989Z",
    "updated_at": "2016-09-29T12:31:26.989Z"
  }, {
    "id": 2,
    "name": "Trying Stuff Until it Works",
    "created_at": "2016-09-29T12:31:26.998Z",
    "updated_at": "2016-09-29T12:31:26.998Z"
  }]

We'll need to do just one more thing before we're good to go on the Rails side.

If we don't set up CORS configuration (cross-origin resource sharing), Rails will complain when we try to hit localhost:3000 from localhost:4200. First, uncomment gem 'rack-cors' in your Gemfile:

# Gemfile

  source 'https://rubygems.org'


  # Bundle edge Rails instead: gem 'rails', github: 'rails/rails'
  gem 'rails', '~> 5.0.0', '>= 5.0.0.1'

  # Use postgresql as the database for Active Record
  gem 'pg', '~> 0.18'

  # Use Puma as the app server
  gem 'puma', '~> 3.0'

  # Build JSON APIs with ease. Read more: https://github.com/rails/jbuilder
  # gem 'jbuilder', '~> 2.5'
  # Use Redis adapter to run Action Cable in production
  # gem 'redis', '~> 3.0'
  # Use ActiveModel has_secure_password
  # gem 'bcrypt', '~> 3.1.7'

  # Use Capistrano for deployment
  # gem 'capistrano-rails', group: :development

# Use Rack CORS for handling Cross-Origin Resource Sharing (CORS), making cross-origin 

AJAX possible

  gem 'rack-cors'

  group :development, :test do
    # Call 'byebug' anywhere in the code to stop execution and get a debugger console
    gem 'byebug', platform: :mri
  end

  group :development do
    gem 'listen', '~> 3.0.5'
    # Spring speeds up development by keeping your application running in the background. Read more: https://github.com/rails/spring
    gem 'spring'
    gem 'spring-watcher-listen', '~> 2.0.0'
  end

  # Windows does not include zoneinfo files, so bundle the tzinfo-data gem
  gem 'tzinfo-data', platforms: [:mingw, :mswin, :x64_mingw, :jruby]
  And then of course bundle install.

  $ bundle install

Then change config/initializers/cors.rb to look like this:

  # config/initializers/cors.rb

  # Be sure to restart your server when you modify this file.

  # Avoid CORS issues when API is called from the frontend app.
  # Handle Cross-Origin Resource Sharing (CORS) in order to accept cross-origin AJAX requests.

  # Read more: https://github.com/cyu/rack-cors

  Rails.application.config.middleware.insert_before 0, Rack::Cors do
    allow do
      origins '*'

      resource '*',
        headers: :any,
        methods: [:get, :post, :put, :patch, :delete, :options, :head]
    end
  end

Don't forget to restart your Rails server.

Step 2: Add an HTTP request to Angular

The first thing we'll do is generate an Angular component that will show us a list of books.

  $ ng generate component book-list

In order to get that component to show up on the home page, edit src/app/app.component.html to look like this:

<!-- src/app/app.component.html -->

  <h1>
    {{title}}
  </h1>

  <app-book-list></app-book-list>

If you now visit http://localhost:4200, you should see not only "app works!" like before but also "book-list works!"

Now let's an a HTTP request to BookListComponent. Let's not worry about showing the HTTP response on the page yet. Let's just console.log the response and see if that much works before we do anything more sophisticated.

// src/app/book-list/book-list.component.ts

import { Component, OnInit } from '@angular/core';
import { Http } from '@angular/http';

@Component({
  selector: 'app-book-list',
  templateUrl: './book-list.component.html',
  styleUrls: ['./book-list.component.css']
})
export class BookListComponent implements OnInit {

  constructor(private http: Http) { }

  ngOnInit() {
    this.http.get('/api/books.json')
      .subscribe(response => console.log(response));
  }

}
Fixing the proxy issue

If you refresh the page now, you'll see an error:

GET http://localhost:4200/api/books.json 404 (Not Found)

This makes sense since Angular currently doesn't have any way to know about our Rails server on port 3000.

We can get Angular to send all XHR requests to port 3000 by configuring a proxy. More precisely, we'll send all XHR requests to port 3000 whose URIs start with /api.

First let's create a file called proxy.conf.json at the Angular project root:

{
  "/api": {
    "target": "http://localhost:3000",
    "secure": "false"
  }
}
Now we want to change the ng serve in package.json to ng serve --proxy-config proxy.conf.json.

Here's my full package.json for reference:

{
  "name": "home-library",
  "version": "0.0.0",
  "license": "MIT",
  "angular-cli": {},
  "scripts": {
    "start": "ng serve --proxy-config proxy.conf.json",
    "lint": "tslint \"src/**/*.ts\"",
    "test": "ng test",
    "pree2e": "webdriver-manager update",
    "e2e": "protractor"
  },
  "private": true,
  "dependencies": {
    "@angular/common": "2.0.0",
    "@angular/compiler": "2.0.0",
    "@angular/core": "2.0.0",
    "@angular/forms": "2.0.0",
    "@angular/http": "2.0.0",
    "@angular/platform-browser": "2.0.0",
    "@angular/platform-browser-dynamic": "2.0.0",
    "@angular/router": "3.0.0",
    "core-js": "^2.4.1",
    "rxjs": "5.0.0-beta.12",
    "ts-helpers": "^1.1.1",
    "zone.js": "^0.6.23"
  },
  "devDependencies": {
    "@types/jasmine": "^2.2.30",
    "angular-cli": "1.0.0-beta.16",
    "codelyzer": "~0.0.26",
    "jasmine-core": "2.4.1",
    "jasmine-spec-reporter": "2.5.0",
    "karma": "1.2.0",
    "karma-chrome-launcher": "^2.0.0",
    "karma-cli": "^1.0.1",
    "karma-jasmine": "^1.0.2",
    "karma-remap-istanbul": "^0.2.1",
    "protractor": "4.0.9",
    "ts-node": "1.2.1",
    "tslint": "3.13.0",
    "typescript": "2.0.2"
  }
}
Kill the process you previously started up using npm start and run npm start again.

$ npm start
If you refresh the page, you should see our two books in the console. Now let's go a step further. We'll create a books property on BookListComponent. When we get the response back from the server, we'll assign this.books to the array we got back.

// src/app/book-list/book-list.component.ts

import { Component, OnInit } from '@angular/core';
import { Http } from '@angular/http';

@Component({
  selector: 'app-book-list',
  templateUrl: './book-list.component.html',
  styleUrls: ['./book-list.component.css']
})
export class BookListComponent implements OnInit {
  books: any;

  constructor(private http: Http) { }

  ngOnInit() {
    this.http.get('/api/books.json')
      .subscribe(response => this.books = response.json());
  }

}
If you were to refresh the page now, you'd see no indication of whether what you just did worked or didn't work. Let's add something to the template to let us see books on the page.

<!-- src/app/book-list/book-list.component.html -->

  <ul>
    <li *ngFor="let book of books">{{ book.name }}</li>
  </ul>

Now, if you refresh the page, you should see our two books listed on the page.

What's next?

There are some issues with our "spike" application:

There are no meaningful tests on the Rails or Angular side.

We haven't deployed to any sort of production environment.

We're showing a list of books, but we don't have a way through the UI to create a new book, edit a book or delete a book.

If you'd like help with those things, I have two suggestions as to where to go.

AngularOnRails.com. That's probably actually where you got this guide. There are a number of free tutorials there that you can use.
My book, Angular for Rails Developers. In addition to covering the same stuff this little guide covers, the book covers deployment and CRUD operations.
And as always, feel free to email me at jason@angularonrails.com if you have questions. (For technical questions, the best way is to create a Stack Overflow question and send me the link.) I'm happy to try to help.

Thanks for reading!

Jason