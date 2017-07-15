# Create a New User and Grant Permissions in MySQL
[how-to-create-a-new-user-and-grant-permissions-in-mysql](https://www.digitalocean.com/community/tutorials/how-to-create-a-new-user-and-grant-permissions-in-mysql)

**Access MySQL**:

	mysql -u root -p

**Query**:	

	mysql> CREATE USER 'newuser'@'localhost' IDENTIFIED BY 'password';

**Check user**:

	mysql> select user from mysql.user;

	+------------------+
	| user             |
	+------------------+
	| root             |
	| root             |
	| debian-sys-maint |
	| dxoooxxx         |
	| root             |
	| srixxx           |
	+------------------+
	6 rows in set (0.00 sec)

	mysql> select user,host from mysql.user;

	+------------------+-----------+
	| user             | host      |
	+------------------+-----------+
	| root             | 127.0.0.1 |
	| root             | ::1       |
	| debian-sys-maint | localhost |
	| dyxxx            | localhost |
	| root             | localhost |
	| srxx             | localhost |
	+------------------+-----------+
	6 rows in set (0.00 sec) 

**Provide the user with access**:

	mysql> GRANT ALL PRIVILEGES ON * . * TO 'newuser'@'localhost';

	Query OK, 0 rows affected (0.00 sec)

**Reload all the privileges**:

	FLUSH PRIVILEGES;

**To find the privilege(s) granted to a particular user**	

	mysql> SHOW GRANTS FOR 'root'@'localhost';