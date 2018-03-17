# Setup Deploy for NodeJS Web

### Using 2 server, Ubuntu 14.04

https://www.digitalocean.com/community/tutorials/how-to-set-up-a-node-js-application-for-production-on-ubuntu-14-04

### Using Single server Ubuntu 14.04 and nginx

https://www.phusionpassenger.com/library/walkthroughs/deploy/nodejs/ownserver/nginx/oss/trusty/deploy_app.html


## The Steps

1. Local: Create Local Git repository.
2. Server: Create Remote Git repository.

		git init --bare --shared reponame.git

3. Local: Add git remote in local app.

		git remote add deploy dyo@example.com:/home/myname/repo/reponame.git

3. Local: Push app to remote repository.

		git push -u deploy master

4. Server: Clone app into folder sites

		git clone /home/myname/repo/reponame.git				

5. Server: Install app dependencies
		
6. Server: Configuring Nginx / Apache Server and Passenger.

		# Make a copy:

		xxx@gstudio:/etc/apache2/sites-available$ sudo cp xxxxxx.conf zzz.conf

7. Open zzz.conf

		sudon nano zzz.conf

8. Edit configuration file of zzz.conf

		<VirtualHost *:80>
		    ServerName example.com
		    ServerAlias www.example.com
		    ServerAdmin webmaster@localhost
		    DocumentRoot /home/xxx/sites/ms/public
		    RailsEnv development
		    ErrorLog ${APACHE_LOG_DIR}/error.log
		    CustomLog ${APACHE_LOG_DIR}/access.log combined
		    <Directory "/home/xxx/sites/ms/public">
		        Options FollowSymLinks
		        Require all granted
		    </Directory>
		</VirtualHost>				


9. Test Drive 

		curl http://example.com/


10. Error

		<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
		<html><head>
		<title>403 Forbidden</title>
		</head><body>
		<h1>Forbidden</h1>
		<p>You don't have permission to access /
		on this server.</p>
		<hr>
		<address>Apache/2.4.7 (Ubuntu) Server at mediosoft.com Port 80</address>
		</body></html>



Solutions:

Change with this: 


		<Directory "/home/dyo/sites/ms/public">
	        Options Indexes FollowSymLinks
	        AllowOverride None
	        Require all granted
	    </Directory>


11. Restart server

		sudo service apache2 restart


12. Error:

		Index of /
		[ICO]	Name	Last modified	Size	Description
		[DIR]	css/	2018-03-11 01:53	-	 
		[DIR]	fonts/	2018-03-11 01:53	-	 
		[DIR]	img/	2018-03-11 01:53	-	 
		[DIR]	js/	2018-03-11 01:53	-	 
		[DIR]	vendors/	2018-03-11 01:53	-	 
		Apache/2.4.7 (Ubuntu) Server at mediosoft.com Port 80

**Solutions**

		.........