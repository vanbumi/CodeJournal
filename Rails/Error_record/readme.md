# Error Collection

## Error 1

Errno::EACCES in Home#index

Showing /home/dyo/sites/msweb/app/views/layouts/application.html.erb where line #7 raised:

Permission denied @ dir_s_mkdir - /home/dyo/sites/msweb/tmp/cache

#### Solution

	chmod 777 /home/dyo/sites/msweb/tmp/cache
	
## 2 Potgres

could not connect to server: Connection refused Is the server running on host "localhost"

#### Solution 1

	Try

	postgres -D /usr/local/var/postgres
	You might see

	FATAL:  lock file "postmaster.pid" already exists
	HINT:  Is another postmaster (PID 449) running in data directory "/usr/local/var/postgres"?
	Then try

	kill -9 PID
	example

	kill -9 449
	And it should start postgres normally
	
#### Solution 2

Try

	postgres -D /usr/local/var/postgres
	You might see

	LOG:  unrecognized configuration parameter "dynamic_shared_memory_type" in file "/usr/local/var/postgres/postgresql.conf" line 127
	FATAL:  configuration file "/usr/local/var/postgres/postgresql.conf" contains errors

**Referrence for this error is**

$ postgres -D /usr/local/var/postgres
launches whatever postgres binary appears first in the $PATH.

In your case it happens to be postgres 9.3.5, presumably from a previous install and/or another installer. That version can't work with the postgresql.conf for 9.4.x because of the new dynamic_shared_memory_type parameter, but more importantly it can't work with a 9.4.x data directory anyway (data formats are not compatible across major versions).

The command which postgres would tell where it is on disk.

Normally the postgres binary for brew should be located in /usr/local/bin/postgres. To avoid conflicting with another postgres, launch it with an absolute path instead of relative:

	$ /usr/local/bin/postgres -D /usr/local/var/postgres

and

	$ /usr/local/bin/postgres -v

**Solution**	

Run this:

	$ /usr/local/bin/postgres -D /usr/local/var/postgres

**Result**

	FATAL:  lock file "postmaster.pid" already exists
	HINT:  Is another postmaster (PID 305) running in data directory "/usr/local/var/postgres"?

and do :

	kill -9 305

error gone !	