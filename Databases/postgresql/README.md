# Postgresql Database

## Important Reference

[help.ubuntu.com/community/PostgreSQL](https://help.ubuntu.com/community/PostgreSQL)

[Backup & Restore via PgAdmin3](http://www.pgadmin.org/docs/dev/backup.html)

## psql commands

go to psql command line:

	sudo -u postgres psql

### show databases:
	\l

### connect to database # to create relations
	
	\c database_name

	database_name# \dt to list all tables
	
	SELECT * FROM table_name;  # to select the table 

### user list:
    
    \du
    
### table list:
    
    \d

### Show version

	postgres=# SELECT version();

### Postgre SQL dump
--------------------

Learn form Sample:

	dyo@pencerahan-sejati:~$ pg_dump cmpbatam_dev -U widyo -h localhost > cmpbatam.sql
	Password: 
	dyo@pencerahan-sejati:~$ ls
	cmpbatam.sql  joomla_bkup.sql  repo  sites

Download it from server to your local:

	scp myusername@university_computer:/home/myusername/file.odt /local/destination/path/	
	
	example:

	scp dyo@pencerahansejati.com:/home/dyo/cmpbatam.sql /home/dyo/backup_db/  DO IT FROM YOUR LOCAL!!

### Postgre SQL Restore
-----------------------

I decided to using GUI PgAdmin
------------------------------

Setup Server

* Open PgAdmin3
* File > Add Server
* Fill in : 
	Name: PencerahanS, 
	host: pencerahan.com 
	username:
	password:

Unable to connect PostgreSQL to remote database using pgAdmin

1. You have to make PostgreSQL listening for remote incoming TCP connections because the default settings allow to listen only for connections on the loopback interface. To be able to reach the server remotely you have to add the following line into the file.
	
	/etc/postgresql/9.1/main/postgresql.conf

	listen_addresses = '*'

2. PostgreSQL by default refuses all connections it receives from any remote address, you have to relax these rules by adding this line to 

	/etc/postgresql/9.1/main/pg_hba.conf:

	host all all 0.0.0.0/0 md5

	This is an access control rule that let anybody login in from any address if he can provide a valid password (the md5 keyword). You can use needed network/mask instead of 0.0.0.0/0 .				

3. When you have applied these modifications to your configuration files you need to restart PostgreSQL server. Now it is possible to login to your server remotely, using the username and password.

Restarting the server
---------------------

After configuring the networking / users you may need to reload the server, here is a suggested command to do so.

	sudo /etc/init.d/postgresql reload

Some settings changes in postgresql.conf require a full restart, which will terminate active connections and abort uncommitted transactions:

	sudo /etc/init.d/postgresql restart	

## Setup on Rails

Create New app

	rails new myapp -d postgresql

Setup on development > config/database.yml

	development:
	  <<: *default
	  host: localhost
	  username: myusername
	  password: mypassword
	  database: mydatabase

Create database:

	$ rake db:create
	$ rake db:migrate
