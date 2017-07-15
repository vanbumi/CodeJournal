## Latihan app codementor
[Codementor](https://www.codementor.io/nodejs/tutorial/build-website-from-scratch-using-expressjs-and-bootstrap)

**Start with** 

	npm init

follow intstruction

**Change entry point (index.js) become**: 

	app.js

**Install express**

	npm install express --save

**Create file app.js**, & create lines code below:

	var express = require("express");
	var app = express();
	var router = express.Router();
	var path = __dirname + '/views/';

	router.use(function (req,res,next) {
	  console.log("/" + req.method);
	  next();
	});

	router.get("/",function(req,res){
	  res.sendFile(path + "index.html");
	});

	router.get("/about",function(req,res){
	  res.sendFile(path + "about.html");
	});

	router.get("/contact",function(req,res){
	  res.sendFile(path + "contact.html");
	});

	app.use("/",router);

	app.use("*",function(req,res){
	  res.sendFile(path + "404.html");
	});

	app.listen(3000,function(){
	  console.log("Live at Port 3000");
	});


**Create folder Views** :

**Create file index.html** :

	<!doctype html>
	<html lang="en">
	<head>
	<meta charset="UTF-8">
	<title>Single page web app using Angularjs</title>
	<script src="//ajax.googleapis.com/ajax/libs/angularjs/1.3.3/angular.min.js"></script>
	<script src="//cdnjs.cloudflare.com/ajax/libs/angular.js/1.3.3/angular-route.min.js"></script>
	<script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
	<link rel="stylesheet" href="http://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css">
	<script src="//maxcdn.bootstrapcdn.com/bootstrap/3.3.1/js/bootstrap.min.js"></script>
	<script src="script.js"></script>
	</head>
	<body>
	<div>
	<div>
	<nav class="navbar navbar-inverse" role="navigation" style="padding-left:130px;">
	       <ul class="nav navbar-nav">
	      <li class="active"><a href="/">Home<span class="sr-only">(current)</span></a></li>
	      <li><a href="/about">About us</a></li>
	      <li><a href="/contact">Contact us</a></li>
	    </ul>
	</nav>
	</div>
	<br/>
	<div class="jumbotron"> <p>
	This is place to put content. You can put slider, short description about your website and place some links for navigation.
	</p></div>
	</div>
	</body>
	</html>

**Start server**:

	node app.js

Check localhost:3000

**Create file about.html**

	<html>
	<head>
	<link rel="stylesheet" href="http://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css">
	<script src="//maxcdn.bootstrapcdn.com/bootstrap/3.3.1/js/bootstrap.min.js"></script>
	</head>
	<body>
	  <div>
	  <div>
	  <nav class="navbar navbar-inverse" role="navigation" style="padding-left:130px;">
	         <ul class="nav navbar-nav">
	        <li><a href="/">Home</a></li>
	        <li class="active"><a href="/about">About us<span class="sr-only">(current)</span></a></li>
	        <li><a href="/contact">Contact us</a></li>
	      </ul>
	</nav>
	</div>
	  <br/>
	  <div class="jumbotron">
	  <p>
	    Put detail description about you and your company.
	  </p>
	</div>
	  </div>
	</body>
	</html>

**Create file Contact.html :**

	<html>
	<head>
	<link rel="stylesheet" href="http://maxcdn.bootstrapcdn.com/bootstrap/3.3.1/css/bootstrap.min.css">
	<script src="//maxcdn.bootstrapcdn.com/bootstrap/3.3.1/js/bootstrap.min.js"></script>
	</head>
	<body>
	  <div>
	  <div>
	  <nav class="navbar navbar-inverse" role="navigation" style="padding-left:130px;">
	         <ul class="nav navbar-nav">
	        <li><a href="/">Home</a></li>
	        <li><a href="/about">About us</a></li>
	        <li class="active"><a href="/contact">Contact us<span class="sr-only">(current)</span></a></li>
	      </ul>
	</nav>
	</div>
	  <br/>
	  <form class="form-horizontal" role="form" style="width: 50%;">
	    <div class="form-group">
	        <label for="name" class="col-sm-2 control-label">Name</label>
	        <div class="col-sm-10">
	            <input type="text" class="form-control" id="name" name="name" placeholder="First & Last Name" value="">
	        </div>
	    </div>
	    <div class="form-group">
	        <label for="email" class="col-sm-2 control-label">Email</label>
	        <div class="col-sm-10">
	            <input type="email" class="form-control" id="email" name="email" placeholder="example@domain.com" value="">
	        </div>
	    </div>
	    <div class="form-group">
	        <label for="message" class="col-sm-2 control-label">Message</label>
	        <div class="col-sm-10">
	            <textarea class="form-control" rows="4" name="message"></textarea>
	        </div>
	    </div>
	    <div class="form-group">
	        <label for="human" class="col-sm-2 control-label">2 + 3 = ?</label>
	        <div class="col-sm-10">
	            <input type="text" class="form-control" id="human" name="human" placeholder="Your Answer">
	        </div>
	    </div>
	    <div class="form-group">
	        <div class="col-sm-10 col-sm-offset-2">
	            <input id="submit" name="submit" type="submit" value="Send" class="btn btn-primary">
	        </div>
	    </div>
	    <div class="form-group">
	        <div class="col-sm-10 col-sm-offset-2">
	            <! Will be used to display an alert to the user>
	        </div>
	    </div>
	</form>
	  </div>
	</body>
	</html>

Run server again:

	node app.js

Visit localhost:3000 and view your first website.

Add folder public

## Deploy!

Change listener to this:

	app.listen(process.env.PORT || 3000);	

Now we goin to deploy it folow this tut [Deployment Server](https://github.com/vanbumi/CodeJournal/tree/master/BasicSetup-WebDevelopment)

