
# Kamfreting error postgresql

createuser: could not connect to database postgres: could not connect to server: No such file or directory

psql: could not connect to server: No such file or directory
	Is the server running locally and accepting
	connections on Unix domain socket "/var/run/postgresql/.s.PGSQL.5432"?

Solution 

	The problem seems to be that LANGUAGE is unset.

#fix for locale issues when connecting to ubuntu servers
	
	export LANG="en_US.utf8"
	export LANGUAGE="en_US.utf8"
	export LC_ALL="en_US.utf8" 

[language-problem-on-ubuntu-14-04](https://www.digitalocean.com/community/questions/language-problem-on-ubuntu-14-04)

---

## error postgres

could not connect to server: Connection refused Is the server running on host "localhost" (::1) and accepting TCP/IP connections on port 5432? could not connect to server: Connection refused Is the server running on host "localhost" (127.0.0.1) and accepting TCP/IP connections on port 5432?

