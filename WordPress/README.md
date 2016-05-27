# Wodpress all about

## 1. Install

* [how-to-install-wordpress-on-ubuntu-14-04](https://www.digitalocean.com/community/tutorials/how-to-install-wordpress-on-ubuntu-14-04)

### Setup database

	cp ~/wordpress/wp-config-sample.php ~/wordpress/wp-config.php

	sudo nano ~/wordpress/wp-config.php

Set db connections

	// ** MySQL settings - You can get this info from your web host ** //
	/** The name of the database for WordPress */
	define('DB_NAME', 'wordpress');

	/** MySQL database username */
	define('DB_USER', 'wordpressuser');

	/** MySQL database password */
	define('DB_PASSWORD', 'password');	

### Download

	$ sudo wget http://wordpress.org/latest.tar.gz

### Unzip

	$ sudo tar -xzvf latest.tar.gz

### Setup Database

	mysql> CREATE DATABASE wp_pencerah;
	Query OK, 1 row affected (0.00 sec)	

	mysql> SET PASSWORD FOR wp_user@localhost= PASSWORD("123456");
	Query OK, 0 rows affected (0.00 sec)

	mysql> GRANT ALL PRIVILEGES ON wp_pencerah.* TO wp_user@localhost IDENTIFIED BY '123456';
	Query OK, 0 rows affected (0.00 sec)

Then refresh MySQL:

	FLUSH PRIVILEGES;
	Query OK, 0 rows affected (0.00 sec)	

Exit out of the MySQL shell:

	exit

Viewv browser

	localhost/...			

--		

## 2. This work: Setup FTP in Ubuntu

* [setup-ftp-server-on-ubuntu-14-04-vsftpd](http://www.krizna.com/ubuntu/setup-ftp-server-on-ubuntu-14-04-vsftpd/)

## 3. How-to-configure-secure-updates-and-installations-in-wordpress-on-ubuntu

* [how-to-configure-secure-updates-and-installations-in-wordpress-on-ubuntu](https://www.digitalocean.com/community/tutorials/how-to-configure-secure-updates-and-installations-in-wordpress-on-ubuntu)

-- 

## Administrator Page

[how-to-add-an-admin-user-to-the-wordpress-database-via-mysql](http://www.wpbeginner.com/wp-tutorials/how-to-add-an-admin-user-to-the-wordpress-database-via-mysql/)