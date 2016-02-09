# Postgresql Database

psql commands
=============

go to psql command line:
	sudo -u postgres psql

show databases:
	\l

connect to database >> create relations
	\c database_name
	    database_name# \dt to list all tables
	    SELECT * FROM table_name;  # to see all inside of table users

user list:
    \du
    
table list:
    \d    