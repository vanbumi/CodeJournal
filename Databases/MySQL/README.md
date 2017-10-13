# MYSQL DUMP
-----------
Good web referense: http://webcheatsheet.com/sql/mysql_backup_restore.php

    $ mysqldump -u root -p Tutorials > tut_backup.sql

MYSQL RESTORE  --------> kagak pake dump
-------------
    $ mysql -u root -p Tutorials < /folder_to_file/tut_backup.sql

DOWNLOAD FROM SERVER TO LOCAL
-----------------------------
    scp dyo@pencerahansejati.com:/home/dyo/cmpbatam.sql /home/dyo/backup_db/

Do it from local!!    

Mysql Workbench
---------------

Install:	

	http://sharadchhetri.com/2013/08/14/install-mysql-workbench-in-ubuntu/

User List
---------

	http://stackoverflow.com/questions/21714869/error-1044-42000-access-denied-for-root-with-all-privileges

Remove Database
---------------

	DROP DATABASE tutorial_database;	

To see User List
----------------

Use this query:

SELECT User FROM mysql.user;
Which will output a table like this:

+-------+
| User  |
+-------+
| root  |
+-------+
| user2 |
+-------+

## Work with Mac

#### Install

    brew install mysql

we've installed your MySQL database without a root password. To secure it run:
    mysql_secure_installation

Result:

MySQL is configured to only allow connections from localhost by default

To connect run:
    mysql -uroot

To have launchd start mysql now and restart at login:
  brew services start mysql
Or, if you don't want/need a background service you can just run:
  mysql.server start
==> Summary
🍺  /usr/local/Cellar/mysql/5.7.19: 322 files, 234.8MB
dyo-mac:grafika dyo-medio$ mysql.server start
Starting MySQL
. SUCCESS! 
