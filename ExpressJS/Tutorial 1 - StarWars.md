# Tutorial ExpressJS StarWars App

## Steps

**Install node**
**Cek node version**: node --version
**Cek npm version**: npm --version
**Create working folder**

	mkdir mySites

**Setup** 

	npm init

And follow intstruction

Change entry point (index.js) become: 

	app.js

**Install express**

	npm install express --save

**Create file app.js**, & create lines code below:

	var express = require('express');

	var app = express();

Try out with:

	console.log("Hey on testing...");	

run on terminal:

	node app.js	

**Setup Routes**:

	// home
	app.get('/', function(req, res){
		res.send("This is test of response on root")
	});

	// sub page
	app.get('/darth', function(req, res){
		res.send("This is test of response on darth page")
	});	

	// server
	app.linsten(3000, function(){
		console.log('App running no port localhost:3000')
	});

Run server on terminal with:

	node app.js

And open browser localhost:3000

### req and res

Use **req** = to access information on url with params,
example:

	var myVar = req.params.myInfoReq;

be like this:	

	// movie_single
	app.get('/star_wars_episode/:episode_number?', function(){
		var episode_number = req.params.episode_number;
		res.send("This is page for episode " + episode_number);
	});

try in browser, by restart the server run with node app.js

	localhost:3000/star_wars_episode/1
	localhost:3000/star_wars_episode/2
	localhost:3000/star_wars_episode/3

We can send HTML, example: &lt;h1&gt;


	app.get('/', function(req, res){
		res.send("<h1>This is test of response on root</h1>")
	});		

**Create Page Not Found**

	app.get('*', function(req, res){
		res.send('This is the page not you looking for')
	});

Check with in browser : 

	localhost:3000/about	

Intall Views Engine **ejs** 	

	npm install ejs --save

And set it up:

	app.set('view engine', 'ejs');

Create new folder views and create file home.ejs inside

In home.ejs create html :

	<h1>This is template for home page</h1>

Change some line on file app.js like below:

	app.get('/', function(req, res){
		res.render('home');
	}); 

Test browser localhost:3000, by restart server

You can add title etc, into it, by pass the object

	app.get('/', function(req, res){
		res.render('home', {
			title: 'Star Wars Movies'
		});

	});
	
And at home.js change as below:

	<h1>This is template for home page</h1>

	<h2><%= title %></h2>

### How create the loop:

	app.get('/', function(req, res){
		res.render('home', {
			title: 'Star Wars Movies',
			movies: ["Movie One", "Movie Two", "Movie Three"]
		});
	});

And in home.ejs

	<ul>
		<% for (var i = 0; i < movies.length; i++) { %>	
			<li><%= movies[i] %></li>
		<% } %>
	</ul>

### Get Bootstrap

Copy basic template

**Install CDN**

Put in head div

	<!-- Latest compiled and minified CSS -->
	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

Put after jQuery on the bottom before close html

	<!-- Latest compiled and minified JavaScript -->
	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>

Change the title:

	<h1><%= title %></h1>

Under **Views** folder create new folder named **partials**

Under **partials** create new file **head.ejs** & **scripts.ejs**

Move code under head div on file **home.ejs** into **head.ejs**

	<meta charset="utf-8">
	<meta http-equiv="X-UA-Compatible" content="IE=edge">
	<meta name="viewport" content="width=device-width, initial-scale=1">

	<title><%= title %></title>

	<!-- Latest compiled and minified CSS -->
	<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css" integrity="sha384-BVYiiSIFeK1dGmJRAkycuHAHRg32OmUcww7on3RYdg4Va+PmSTsz/K68vbdEjh4u" crossorigin="anonymous">

	<!-- Bootstrap -->
	<link href="css/bootstrap.min.css" rel="stylesheet">	
Move all script below page home.ejs into file scripts.ejs

	<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
	<!-- Latest compiled and minified JavaScript -->
	<script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js" integrity="sha384-Tc5IQib027qvyjSMfHjOMaLkfuWVxZxUPnCJA7l2mCWNIpG9mGCD8wGNIcPD7Txa" crossorigin="anonymous"></script>

and include those file in home.ejs

	<% include partials/head.ejs %>
	<% include partials/scripts.ejs %>

**Create new folder public on root app**

	public >
		images
		stylesheets >
			styles.css
		javascripts

**Create new folder named routes and new file : index.ejs**

	routes >
		index.js

**Create new file on the root named movies.json**

Copy json file from https://github.com/RyanHemrick/star_wars_movie_app

Move all function into routes > index.js to make them organize.

routes > index.js

	// home
	exports.home = function(req, res){
	  var movies = moviesJSON.movies;
	  res.render('home', {
	    title : "Star Wars Movies",
	    movies : movies
	  });
	};

	// movie single
	exports.movie_single = function(req, res){
	  var episode_number = req.params.episode_number;
	  res.send("This is the Page for episode " + episode_number);
	};

	// not found
	exports.notFound = function(req, res){
	  res.send("This not Page you looking for!")
	};
	
Access those function from app.js with update app.js below:

	var routes = require('./routes');
	
	// home
	app.get('/', routes.home);

	// movie single
	app.get('/star_wars_episode/:episode_number?', routes.movie_single);

	// not found
	app.get('*', routes.notFound);

Copy all images from the github and past under public > images

Include or require data json in the routes > index.js by

	var moviesJSON = require('../movies.json');

Create variable movies routes > index.js, and pasing in home render function, update file as below:

	exports.home = function(req, res){

	  var movies = moviesJSON.movies;

	  res.render('home', {
	    title : "Star Wars Movies",
	    movies : movies
	  });
	};

And create loop in home.ejs file

	<% for (var i = 0; i < movies.length; i++) { %>
	    <img src="/images/<%= movies[i].poster %>" alt="" class="img-responsive" />
	<% } %>

Dont forget to create module path in app.js file

	var path = require('path');

and create static folder (public)

	app.use(express.static(path.join(__dirname, 'public')));

Test the images show by restart node app.js and browser localhost:3000

Copy file styles.css from the github, paste into my local file styles.css

Add div on file home.js

	<div id="hero-image">
		<h1 id="hero-title"><%= title %></h1>
	</div>

Dont forget to write references link on head.ejs

Get google fonts
	
	https://fonts.google.com/

	<link href="https://fonts.googleapis.com/css?family=Montserrat:400,700" rel="stylesheet">

Check browser localhost:3000

Update home.js like below:

	<div id="posters-wrapper" class="content-padding clearfix">

	    <% for (var i = 0; i < movies.length; i++) { %>
	      <div class="poster">
	          <img src="/images/<%= movies[i].poster %>" alt="" class="img-responsive" />
	      </div>
	    <% } %>

	</div>

Check browser localhost:3000

Navigation - Create new file header.ejs inside folder partials, write this code:

	<div class="navbar navbar-fixed-top">

	  <div class="content-padding">
	    <ul class="nav navbar-nav navbar-right">
	      <li><a href="/">Home</a></li>
	      <li class="dropdown"><a href="#" class="dropdown-toggle" data-toggle="dropdown">Movies <i class="fa fa-chevron-down" aria-hidden="true"></i></a>
	        <ul class="dropdown-menu">
	          <% for (var i = 0; i < movies.length; i++) { %>
	            <li> <a href="#" class="episode_link"><%= movies[i].title %></a></li>
	          <% } %>
	        </ul>
	      </li>
	    </ul>
	  </div>

	</div>

Do not forget to include header.ejs file into home.ejs

	<% include partials/header.ejs %>

And add CDN **Font Awesome** on head.ejs file

	<script src="https://use.fontawesome.com/22fd7f8efa.js"></script>


## Deploy

Change listener to this:

	app.listen(process.env.PORT || 3000);		

next video 1 55:25	






