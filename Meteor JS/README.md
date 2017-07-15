# Meteor JS

* [Video Tutorial - Sasi Kanth](https://www.youtube.com/channel/UCuK5KMmdJgMiPI733DOKauw)

## Steps 

### Install

[Installation](https://www.meteor.com/install)

	curl https://install.meteor.com/ | sh 

### Todo App with React 

#### Creating an app

Creating your first app, create a simple app to manage a 'to do' list and collaborate with others on those tasks.

To create the app, open your terminal and type:

	$ cd sites_meteor
	$ sites_meteor> meteor create simple-todos

This will create a new folder called simple-todos with all of the files that a Meteor app needs:

	client/main.js        # a JavaScript entry point loaded on the client
	client/main.html      # an HTML file that defines view templates
	client/main.css       # a CSS file to define your app's styles
	server/main.js        # a JavaScript entry point loaded on the server
	package.json          # a control file for installing NPM packages
	.meteor               # internal Meteor files
	.gitignore            # a control file for git	

To run the newly created app:

	cd simple-todos
	meteor npm install
	meteor

Open your web browser and go to http://localhost:3000 to see the app running.

You can play around with this default app for a bit before we continue. For example, try editing the text in &lt;h1&gt; inside client/main.html using your favorite text editor. When you save the file, the page in your browser will automatically update with the new content. We call this "hot code push".

#### Defining views with React components

To start working with React as our view library, let's add some NPM packages which will allow us to get started with React.

Open a new terminal in the same directory as your running app, and type:

	meteor npm install --save react react-dom


