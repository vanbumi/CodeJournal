# Error Collection

## Error 1

Errno::EACCES in Home#index

Showing /home/dyo/sites/msweb/app/views/layouts/application.html.erb where line #7 raised:

Permission denied @ dir_s_mkdir - /home/dyo/sites/msweb/tmp/cache

#### Solution

	chmod 777 /home/dyo/sites/msweb/tmp/cache
	
## 2 Potgres

could not connect to server: Connection refused Is the server running on host "localhost"

#### Solution

	Try

	postgres -D /usr/local/var/postgres
	You might see

	FATAL:  lock file "postmaster.pid" already exists
	HINT:  Is another postmaster (PID 449) running in data directory "/usr/local/var/postgres"?
	Then try

	kill -9 PID
	example

	kill -9 419
	And it should start postgres normally
	
	