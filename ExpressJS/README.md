# Express JS

## Setup Server

* [How To Install Express, a Node.js Framework, and Set Up Socket.io on a VPS | DigitalOcean](https://www.digitalocean.com/community/tutorials/how-to-install-express-a-node-js-framework-and-set-up-socket-io-on-a-vps)
* [How To Set Up a Node.js Application for Production on Ubuntu 14.04](https://www.digitalocean.com/community/tutorials/how-to-set-up-a-node-js-application-for-production-on-ubuntu-14-04)
* [How To Install Node.js on an Ubuntu 14.04 server](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-an-ubuntu-14-04-server)
* [Hosting Node.js app to DigitalOcean Server](https://codeforgeek.com/2016/03/hosting-node-js-app-to-digitalocean-server/)

* [Deploy Aplikasi Node.js Menggunakan PM2](https://www.codepolitan.com/tutorial/deploy-aplikasi-nodejs-menggunakan-pm2-57bbfb6931a1d-4)


### Loop

	<ul>
	  <% for (var i = 0; i < movies.length; i++) { %>
	  <li><%= movies[i] %></li>
	  <% } %>
	</ul>

### Star Wars Movie App

[Github](https://github.com/RyanHemrick/star_wars_movie_app)

## Error deployed Digital Ocean

Solution:

On server:

npm and other applications will be looking for the node executable, and not necessarily nodejs. Create a symlink pointing from node to nodejs.

	% which nodejs
	/usr/bin/nodejs
	% ln -s /usr/bin/nodejs /usr/bin/node

Ref:  

	https://amodernstory.com/2015/06/07/creating-a-website-with-nodejs-nginx-and-digital-ocean/	

Also dont forget point to public folder on server conf. virtual host:

	DocumentRoot /home/user/myapp/public


## Deploy

Change listener to production:

	app.listen(process.env.PORT || 3000);	