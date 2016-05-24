# Wodpress all about

How to install in Local

* [how-to-configure-secure-updates-and-installations-in-wordpress-on-ubuntu](https://www.digitalocean.com/community/tutorials/how-to-configure-secure-updates-and-installations-in-wordpress-on-ubuntu)

Download

	$ sudo wget http://wordpress.org/latest.tar.gz

Unzip

	$ sudo tar -xzvf latest.tar.gz

Setup Database

	mysql> CREATE DATABASE wp_pencerah;
	Query OK, 1 row affected (0.00 sec)	

	mysql> SET PASSWORD FOR wp_user@localhost= PASSWORD("123456");
	Query OK, 0 rows affected (0.00 sec)

	mysql> GRANT ALL PRIVILEGES ON wp_pencerah.* TO wp_user@localhost IDENTIFIED BY '123456';
	Query OK, 0 rows affected (0.00 sec)

Then refresh MySQL:

	FLUSH PRIVILEGES;
	Query OK, 0 rows affected (0.00 sec)	

## This work: Setup FTP in Ubuntu

* [setup-ftp-server-on-ubuntu-14-04-vsftpd](http://www.krizna.com/ubuntu/setup-ftp-server-on-ubuntu-14-04-vsftpd/)