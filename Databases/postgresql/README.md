# Postgresql Database

psql commands
=============

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

	

Learn form Sample:

	dyo@pencerahan-sejati:~$ pg_dump cmpbatam_dev -U widyo -h localhost > cmpbatam.sql
	Password: 
	dyo@pencerahan-sejati:~$ ls
	cmpbatam.sql  joomla_bkup.sql  repo  sites

Download it from server to your local:

	scp myusername@university_computer:/home/myusername/file.odt /local/destination/path/	
	
	example:

	scp dyo@pencerahansejati.com:/home/dyo/cmpbatam.sql /home/dyo/backup_db/  DO IT FROM YOUR LOCAL!!



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
