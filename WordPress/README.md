# Wodpress all about

# 1. Install

* [how-to-install-wordpress-on-ubuntu-14-04](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-14-04)

## STEPS (you might download & install stright to server ???)

### 1. Download Latest Wordpress

	$ sudo wget http://wordpress.org/latest.tar.gz

### 2. Unzip

	$ sudo tar -xzvf latest.tar.gz

### 3. Setup Database

#### Create database

	mysql> CREATE DATABASE wp_pencerah;
	Query OK, 1 row affected (0.00 sec)	

#### Create User

**To see User List**

	SELECT User FROM mysql.user;

**Create user**	

	CREATE USER wordpressuser@localhost IDENTIFIED BY 'password';

#### Create Password

	mysql> SET PASSWORD FOR wp_user@localhost= PASSWORD("123456");
	Query OK, 0 rows affected (0.00 sec)

#### Create Permission

At this point, you have a database and a user account, each made specifically for WordPress. However, these two components have no relationship yet. The user has no access to the database.

Let's fix that by granting our user account access to our database with this command:

	mysql> GRANT ALL PRIVILEGES ON wp_pencerah.* TO wp_user@localhost IDENTIFIED BY '123456';
	Query OK, 0 rows affected (0.00 sec)

Then refresh MySQL:

	FLUSH PRIVILEGES;
	Query OK, 0 rows affected (0.00 sec)	

Exit out of the MySQL shell:

	exit

#### Setup wp-config file

	cp ~/wordpress/wp-config-sample.php ~/wordpress/wp-config.php

	sudo nano ~/wordpress/wp-config.php

#### Set db connections (database_name, username, password)

	// ** MySQL settings - You can get this info from your web host ** //
	/** The name of the database for WordPress */
	define('DB_NAME', 'wordpress');

	/** MySQL database username */
	define('DB_USER', 'wordpressuser');

	/** MySQL database password */
	define('DB_PASSWORD', 'password');		

Viewv browser

	localhost/...			

#### Deploy to VPS

1. [Setup Server](https://github.com/vanbumi/CodeJournal/tree/master/BasicSetup-WebDevelopment) 

Error when deploy

	<?php
	/**
	 * Front to the WordPress application. This file doesn't do anything, but loads
	 * wp-blog-header.php which does and tells WordPress to load the theme.
	 *
	 * @package WordPress
	 */

	/**
	 * Tells WordPress to load the WordPress theme and output it.
	 *
	 * @var bool
	 */
	define('WP_USE_THEMES', true);

	/** Loads the WordPress Environment and Template */
	require( dirname( __FILE__ ) . '/wp-blog-header.php' );

![wp error](http://res.cloudinary.com/medioxtra/image/upload/v1470821371/wp-eror-deploy_a7fo8m.png)

Solution

try this next:

	https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-14-04

---		

# 2. This work: Setup FTP in Ubuntu

* [setup-ftp-server-on-ubuntu-14-04-vsftpd](http://www.krizna.com/ubuntu/setup-ftp-server-on-ubuntu-14-04-vsftpd/)

# 3. How-to-configure-secure-updates-and-installations-in-wordpress-on-ubuntu

* [how-to-configure-secure-updates-and-installations-in-wordpress-on-ubuntu](https://www.digitalocean.com/community/tutorials/how-to-configure-secure-updates-and-installations-in-wordpress-on-ubuntu)

Error : Public and Private keys incorrect for wp-user

Solution:
https://www.digitalocean.com/community/questions/wordpress-ssh-public-and-private-keys-incorrect-for-wp-user

	SOLVED!!!

	I'm posting this here so that if someone else has this frustrating problem this might solve it.

	Here is what I found:

	Try to give www-data permission in wordpress directory:

	cd /yourwordpress_dir/
	sudo chown -R www-data:www-data *

	In my case, I had to cd /var/www/html and then sudo chown -R www-data:www-data *

	:-)

--- 

## Administrator Page

[how-to-add-an-admin-user-to-the-wordpress-database-via-mysql](http://www.wpbeginner.com/wp-tutorials/how-to-add-an-admin-user-to-the-wordpress-database-via-mysql/)

### Move web from root to folder:

* [Cara Pindahkan Folder WordPress dari Root ke Subfolder di cPanel](https://gegeriyadi.com/cara-pindahkan-folder-wordpress-dari-root-ke-subfolder)
* [How to change WordPress site address (URL)](https://www.namecheap.com/support/knowledgebase/article.aspx/9201/2187/how-to-change-wordpress-site-address-url)