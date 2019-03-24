# Error Collection

## Error 1

Errno::EACCES in Home#index

Showing /home/dyo/sites/msweb/app/views/layouts/application.html.erb where line #7 raised:

Permission denied @ dir_s_mkdir - /home/dyo/sites/msweb/tmp/cache

#### Solution

	chmod 777 /home/dyo/sites/msweb/tmp/cache
	
## Error 2: Potgres

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


## Error 3

PG::ConnectionBad (could not connect to server: Connection refused Is the server running on host "localhost" (::1) and accepting TCP/IP connections on port 5432?

**Solution**

It could be as simple as a stale PID file. It could be failing silently because your computer didn't complete the shutdown process completely which means postgres didn't delete the PID (process id) file.

The PID file is used by postgres to make sure only one instance of the server is running at a time. So when it goes to start again, it fails because there is already a PID file which tells postgres that another instance of the server was started (even though it isn't running, it just didn't get to shutdown and delete the PID).

1. To fix it remove/rename the **PID file**. Find the postgres data directory. On a MAC using homebrew it is /usr/local/var/postgres/, other systems it might be /usr/var/postgres/.

2. To make sure this is the problem, look at the log file (server.log). On the last lines you will see:

		FATAL: lock file "postmaster.pid" already exists
		HINT: Is another postmaster (PID 347) running in data directory "/usr/local/var/postgres"?

3. If so, rm postmaster.pid.

4. Restart your server. On a mac using launchctl (with homebrew) the following commands will restart the server.

		launchctl unload homebrew.mxcl.postgresql.plist  
		launchctl load -w homebrew.mxcl.postgresql.plist

OR on newer versions of Brew

	brew services restart postgresql
	