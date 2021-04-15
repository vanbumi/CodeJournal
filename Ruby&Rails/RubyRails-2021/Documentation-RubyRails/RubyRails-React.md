# Ruby on Rails React

## Rails 6

## Install Materialize for Rails 6

Ref: https://titanwolf.org/Network/Articles/Article?AID=26742bed-4f9b-44ed-9477-61ca521843b7#gsc.tab=0

1. Materialize Gem, add to Gemfile:

   ```ruby
   # materialize
   
   gem 'materialize-sass'
   ```

2. bundle install

3. Import materialize in the app/assets/stylesheets/application.scss

   ```ruby
   @import 'materialize';
   ```

4. Test with code bellow at index.html.erb :

   ```ruby
   <% # Omitted%> 
    <div class="input-field">
   
     <input type="text" id="name" name='name'>
   
     <label for="name">name</label>
    </div>
   ```

5. Install materialize-css in yarn

   ```ruby
   yarn add materialize-css
   ```

6. Append the following to app/javascript/packs/application.js

  ```ruby
  import 'materialize-css/dist/js/materialize'
  ```

7. Install the jquery in yarn

	```ruby
	yarn add jquery
	```

Ref : https://www.botreetechnologies.com/blog/introducing-jquery-in-rails-6-using-webpacker

8. Tambahkan code ini di environment.js

   ```javascript
   const webpack = require('webpack')
   environment.plugins.prepend('Provide',
     new webpack.ProvidePlugin({
       $: 'jquery/src/jquery',
       jQuery: 'jquery/src/jquery'
     })
   )
   ```

9. Kemudian import jquery di file javascript/packs/application.js :

   ```javascript
   import "jquery"
   ```

Now you should be able to use jquery in your Rails 6 application.



#### Install Material Icons

https://github.com/Angelmmiguel/material_icons

* Gemfile :

```
gem 'material_icons'
```

* application.scss :

  ```
  *= require material_icons
  ```

RESTART SERVER agar material icons bisa bekerja.



#### Add Nav

...

#### Add Container

https://materializecss.com/grid.html

CSS > Grid

#### Add Footer

> **BACA INI**: We use flexbox to structure our html so that the footer is always on the bottom of the page. It is important to keep the structure of your page within the 3 HTML5 tags: `<header>`, `<main>`, `<footer>`

Contoh :

```erb
<header>
	<nav>
  	....
  </nav>
</header>

<main>
	<container>
  	<%= yield %>
  </container>
</main>

<footer>
	Copyright blah
</footer>
```

Dan tambahkan style pada /univ_app/app/assets/stylesheets/custom.css.scss

```scss
body {
    display: flex;
    min-height: 100vh;
    flex-direction: column;
  }

main {
  flex: 1 0 auto;
}
```



#### Add Menu Dropdown

https://materializecss.com/navbar.html

Tempatkan code dropdown diatas nav :

```html
<ul id="dropdown1" class="dropdown-content">
  <li><a href="#!">one</a></li>
  <li><a href="#!">two</a></li>
  <li class="divider"></li>
  <li><a href="#!">three</a></li>
</ul>
<nav>
  <div class="nav-wrapper">
    <a href="#!" class="brand-logo">Logo</a>
    <ul class="right hide-on-med-and-down">
      <li><a href="sass.html">Sass</a></li>
      <li><a href="badges.html">Components</a></li>
      <!-- Dropdown Trigger -->
      <li><a class="dropdown-trigger" href="#!" data-target="dropdown1">Dropdown<i class="material-icons right">arrow_drop_down</i></a></li>
    </ul>
  </div>
</nav>
```

Tempatkan kode jquery pada file packs/application.js

```javascript
$( document ).on('turbolinks:load', function() {
    $(".dropdown-trigger").dropdown();
})
```

**Trigger dropdown menu on click**

By default, the dropdown menu is activated by hovering over the dropdown trigger. To activate the dropdown menu on click, pass { hover: false } into the above dropdown() function.

```javascript
$( document ).on('turbolinks:load', function() {
    $(".dropdown-trigger").dropdown({ hover: false });
})
```



#### Add Mobile Collapse Button

https://materializecss.com/navbar.html

Tambahkan kode dibawah ini dibawah ```class="brand-log"```

```html
<a href="#!" class="brand-logo">Logo</a>

// Tambahkan ini 
<a href="#" data-target="mobile-demo" class="sidenav-trigger"><i class="material-icons">menu</i></a>
```

Dan tambahkan menu sidenav dibawah element ```<ul>``` diatas nya:

```html
<ul id="dropdown1" class="dropdown-content">
  <li><a href="#!">one</a></li>
  <li><a href="#!">two</a></li>
  <li class="divider"></li>
  <li><a href="#!">three</a></li>
</ul>
<nav>
  <div class="nav-wrapper">
    <a href="#!" class="brand-logo">Logo</a>
    <a href="#" data-target="mobile-demo" class="sidenav-trigger"><i class="material-icons">menu</i></a>
    <ul class="right hide-on-med-and-down">
      <li><a href="sass.html">Sass</a></li>
      <li><a href="badges.html">Components</a></li>
      <li><a href="collapsible.html">Javascript</a></li>
      <li><a href="mobile.html">Mobile</a></li>
    </ul>
    //Tambahkan ini 
    <ul class="sidenav" id="mobile-demo">
      <li><a href="sass.html">Sass</a></li>
      <li><a href="badges.html">Components</a></li>
      <li><a href="collapsible.html">Javascript</a></li>
      <li><a href="mobile.html">Mobile</a></li>
    </ul>
  </div>
</nav>
```

Tambahkan kode jquery ini diatas kode jquery sebelum nya di file application.js

```javascript
$('.sidenav').sidenav();
```

Kodenya menjadi seperti ini :

```javascript
$( document ).on('turbolinks:load', function() {
  	$('.sidenav').sidenav();
    $(".dropdown-trigger").dropdown({ hover: false });
})
```

Tambahkan kode trigger dropdown 1 lagi dibawanya dan rubah id nya menjadi ```id="dropdown1"```

Kode lengkap nya seperti dibawah ini :

```html
<header>
  <ul id="dropdown1" class="dropdown-content">
    <li><a href="#!">one</a></li>
    <li><a href="#!">two</a></li>
    <li class="divider"></li>
    <li><a href="#!">three</a></li>
  </ul>
  <ul id="dropdown2" class="dropdown-content">
    <li><a href="#!">one</a></li>
    <li><a href="#!">two</a></li>
    <li class="divider"></li>
    <li><a href="#!">three</a></li>
  </ul>
  <nav>
    <div class="container">
      <div class="nav-wrapper">
        <a href="#" class="brand-logo right">TechCademy</a>
        <a href="#" data-target="mobile-demo" class="sidenav-trigger"><i class="material-icons">menu</i></a>
        <!-- menu 1 top -->
        <ul id="nav-mobile" class="left hide-on-med-and-down">
          <li><a href="#">Courses</a></li>
          <li><a href="#">Enrolments</a></li>
          <!-- Dropdown Trigger -->
          <li><a class="dropdown-trigger" href="#!" data-target="dropdown1">Account<i class="material-icons right">arrow_drop_down</i></a></li>
        </ul>
        <!-- menu 2 burger -->
        <ul class="sidenav" id="mobile-demo">
          <li><a href="#">Sass</a></li>
          <li><a href="#">Components</a></li>
          <li><a href="#">Javascript</a></li>
          <!-- Dropdown Trigger -->
          <li><a class="dropdown-trigger" href="#!" data-target="dropdown2">Account<i class="material-icons right">arrow_drop_down</i></a></li>
        </ul>
      </div>
    </div>
  </nav>
</header>
```



#### Merubah warna navbar

Tambahkan class pada nav :

```html
<nav class="navbar blue lighten-1">
```

Warna lain kamu dapat lihat disini: https://materializecss.com/color.html

last vid 44 crud from the backend