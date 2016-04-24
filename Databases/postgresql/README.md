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

### SQL dump

	http://www.postgresql.org/docs/9.4/static/backup-dump.html	   
	
	http://www.thegeekstuff.com/2009/01/how-to-backup-and-restore-postgres-database-using-pg_dump-and-psql/



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
