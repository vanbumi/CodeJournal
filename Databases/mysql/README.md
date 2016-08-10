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

