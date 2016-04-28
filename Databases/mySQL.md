# sMSYQL DUMP
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