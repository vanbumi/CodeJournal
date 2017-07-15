# Building a Simple CRUD Application with Express and MongoDB
[crud-express-mongodb-part1](https://zellwk.com/blog/crud-express-mongodb/)
[crud-express-mongodb-part2](https://zellwk.com/blog/crud-express-and-mongodb-2/)

To check if you have Node installed, open up your command line and run the following code:

	$ node -v

Create work folder:

	$ mkdir simplecrud

	cd simplecrud

	$ npm init

create a file called **server.js** to run node.

	touch server.js

Write:

	console.log('May Node be with you')

Running node: 

	$ node server.js

Install Express

	$ npm install express --save

Write in server.js

	const express = require('express');
	const app = express();

create a server:

	app.listen(3000, function() {
	  console.log('listening on 3000')
	})	

	app.get('/', function(req, res){
	  res.sendFile(__dirname + 'index.html');	
	});

Create file index.html

	touch index.html

and write bellow:

	<html>
	<head>
	    <meta charset="UTF-8">
	    <title>My App</title>
	</head>
	<body>
	    May Node & Express be with you.
	</body>
	</html>		

Install Nodemon
Nodemon is for restarts the server automatically

	$ npm install nodemon --save-dev

**--save-dev** flag here is because we’re only using Nodemon when we’re developing.

Add scripts 
Edit file package.json as below:

	{
	  "name": "simplecrud",
	  "version": "1.0.0",
	  "description": "",
	  "main": "index.js",
	  "scripts": {
	    "test": "echo \"Error: no test specified\" && exit 1"
	  },
	  "author": "Dyo Medio",
	  "license": "ISC",
	  "dependencies": {
	    "express": "^4.14.0"
	  },
	  "devDependencies": {
	    "nodemon": "^1.10.2"
	  },
	  "scripts": {
	    "dev": "nodemon server.js"
	  }
	} 	

to be continnue