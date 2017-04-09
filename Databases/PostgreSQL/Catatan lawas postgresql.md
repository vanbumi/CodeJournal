POSTGRESQL
==========

install postgresql disini:
--------------------------
    https://www.digitalocean.com/community/tutorials/how-to-use-postgresql-with-your-ruby-on-rails-application-on-ubuntu-14-04
    

NEW RAILS APP
-------------

    rails new medioklinik -d postgresql
    

How To Create, Remove, & Manage Tables in PostgreSQL on a Cloud Server
----------------------------------------------------------------------
https://www.digitalocean.com/community/tutorials/how-to-create-remove-manage-tables-in-postgresql-on-a-cloud-server


How to Install and Log Into PostgreSQL on Ubuntu
------------------------------------------------

Install PostgreSQL
------------------
If you don't already have PostgreSQL installed, let's do that now.

First, update apt-get:

    sudo apt-get update

Then install PostgreSQL and its development libraries:

    sudo apt-get install postgresql postgresql-contrib libpq-dev

PostgreSQL is now installed but you should create a new database user, that your Rails application will use.


Create Database User
--------------------
Create a PostgreSQL superuser user with this command (substitute the highlighted word with your own username):

    sudo -u postgres createuser -s demo

If you want to set a password for the database user, enter the PostgreSQL console with this command:
----------------------------------------------------------------------------------------------------

    sudo -u postgres psql

The PostgreSQL console is indicated by the postgres=# prompt. At the PostgreSQL prompt, enter this command to set the password for the database user that you created:

    \password demo

Enter your desired password at the prompt, and confirm it.

Now you may exit the PostgreSQL console by entering this command:

    \q

---

POSTGRESQL
----------

to know Version :

    $ psql --version

    psql (PostgreSQL) 9.3.9

https://help.ubuntu.com/community/PostgreSQL

INSTALL PGADMIN3
----------------
    
    sudo apt-get install pgadmin3

HOW TO USE PGADMIN3
--------------------

    http://www.pgadmin.org/docs/1.4/using.html

---

psql commands
-------------

go to psql command line:

	sudo -u postgres psql

show databases:

	\l

connect to database >> create relations

	\c database_name
	    indorails_dev=# >> type \dt to list all tables
	    SELECT * FROM table_name; >> to see all inside of table users

user list:

    \du
    
table list:

    \d    

perintah SELECT:

	$ SELECT * FROM users where "id" = 1;

update sql query:

    http://www.postgresql.org/docs/9.1/static/sql-update.html

Next we need to setup our postgres user:

    sudo su - postgres     #is command to >> postgres@sraccounts:~$
    createuser --pwprompt
    exit


PROBLEM WITH LOCALE
-------------------

    http://askubuntu.com/questions/50621/cannot-connect-to-postgresql-on-port-5432

Tutorial postgresql
-------------------

    https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-14-04
    
    
SQL Dump
--------
    
    pg_dump dbname > outfile
    
Restoring the Dump
------------------
    
    psql dbname < infile
    
CEK VERSION
-----------
    
    - psql --version
    - SELECT version();
