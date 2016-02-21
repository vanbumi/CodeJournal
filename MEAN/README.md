# MEAN Stack for Developer

Link References:

* http://meanjs.org/
* http://mean.io
* http://gruntjs.com/

## Getting Started

Install globaly Bower

	sudo npm install -g bower


Install Grunt

	sudo npm install -g grunt-cli

Install Yo	

	sudo npm install -g yo

Install MeanJS

	sudo npm install -g generator-meanjs

Creating New App using Yo MeanJS, navigate to your project name and type bellow command to generate new app

	mymean_app$	yo meanjs

it will take couple minutes!

When installation done, navigate to folder mean and run grunt

	$ cd mean
	$ grunt

When your database is setup you will see bellow and open localhost:3000

	yo@dyo-medio:~/sites_mean/myMEANProject/mean$ grunt
Running "env:dev" (env) task

Running "sass:dist" (sass) task

Running "less:dist" (less) task

Running "jshint:all" (jshint) task
>> 89 files lint free.

Running "eslint:target" (eslint) task

Running "csslint:all" (csslint) task
>> 2 files lint free.

Running "mkdir:upload" task

Running "copy:localConfig" (copy) task


Running "concurrent:default" (concurrent) task
    Running "nodemon:dev" (nodemon) task
    [nodemon] 1.9.0
    [nodemon] to restart at any time, enter `rs`
    [nodemon] watching: server.js config/**/*.js modules/*/server/**/*.js
    [nodemon] starting `node --debug server.js`
    debugger listening on port 5858
    Running "watch" task
    Waiting...
    
    
    --
    MEAN.JS - Development Environment
    Environment:			development
    Port:				3000
    Database:				mongodb://localhost/mean-dev
    App version:			0.4.2
    MEAN.JS version:			0.4.2
    --

Don't forget to activate your mongodb on your local computer

Done!






