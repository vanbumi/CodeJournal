### Copy ubuntu

	$ sudo cp dbck.git dbck_mysql.git

	cp: omitting directory 'dbck.git'

#### Solved:

For folder copy use -r (--recursive)

	$ sudo cp -r dbck.git dbck_mysql.git
