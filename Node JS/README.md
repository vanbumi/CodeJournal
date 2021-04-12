# Node JS

Apa itu Node.js

Node.js bukan bahasa programing dan bukan framework,
Node.js adalah JavaScript runtime yang dibangun didalam JavaScript engine v8, engine yang sama yang digunakan oleh Google Chrome, yang menjadikan Google Chrome powerful dan sangat cepat.

Apa itu runtime? Node menjadikan JavaScript berjalan secara single proses didalam mesin anda, v8 engine yang ditulis dengan c++ menjadikan JavaScript dan meng-copilenya menjadi bahasa mesin yang cepat dan dimengerti oleh komputer.

Node membuat JavaScript menjadi server side teknologi, seperti PHP, Rails, Java, Python dsb.

Node adalah Teknologi Cross Platform, yang berjalan pada semua Operating System, seperti Windows, Mac dan Linux.

Node membangun aplikasi berskala besar dengan sangat cepat dan mendukung real-time aplikasi.

Bila anda memiliki pengalaman cukup dengan Node.js akan menjadikan anda pada jajaran Top Skill yang banyak dibutuhkan oleh Teknologi saat ini di dunia.

Apa yang bisa kita lakukan dengan Node?

* Manipulasi file pada filesystem.
* Membangun web servers.
* Query database (MongoDB, MySQL, Postgres, Redis dll)
* Powerfull APIs & Backend interfaces.
* Powerfull server side apps dengan render view.
* Real-time service.

### Getting Start Server!

cd to your project workspace folder

Create new directory for your new app

	$ mkdir myApp

Navigate to myApp folder

	cd myApp

Create JavaScript file named server.js and add following code:

	var express = require('express');   
	var app = express();
	
	app.get('/', function (req, res) {
	   res.send("Hello form server.js")
	});
	
	app.listen(3000);
	console.log("Server running on port 3000");

On the same folder now install express

    $ npm init
    
    $ npm install express --save

Run the server

	$ node server

Open localhost:3000    

Walahhh :)

### Setup static page (html template)

Replace server.js with this code:

	var express = require('express');
	var app = express();
	
	* app.use(express.static(__dirname + '/public'));
	
	app.listen(3000);
	console.log("Server running on port 3000");

Create folder public

	mkdir public

Under public folder create html file named index.html

	touch index.html

On index.html write this code for test:

	<!DOCTYPE html>
	<html lang="en">
	<head>
	    <meta charset="UTF-8">
	    <title>myApp</title>
	</head>
	<body>
	    <h1>My NodeJS Application</h1>
	</body>
	</html>

Refresh the server and run again

	node server

### Setup AngularJS

Add this CDN inside index.html file

	https://ajax.googleapis.com/ajax/libs/angularjs/1.5.0/angular.min.js        

Put link CDN before closing tag body as sample bellow:

	<!DOCTYPE html>
	<html>
	<head>
	    <meta charset="UTF-8">
	    <title>Contact List App</title>
	</head>
	<body>
	    <h1>myApp</h1>


	    * <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.5.0/angular.min.js"></script>
	</body>
	</html>

And test it with Angular sintax

Done :)	

## Update NodeJS

Used the following instructions to upgrade from NodeJS version on a Mac & LInux.

Clear NPM's cache:

	sudo npm cache clean -f

Install a little helper called 'n'

	sudo npm install -g n

Install latest stable NodeJS version

	sudo n stable

Alternatively pick a specific version and install like this:

	sudo n 0.8.20 (version option)



## Node Version Manager



tutorial link: https://www.keycdn.com/blog/node-version-manager

