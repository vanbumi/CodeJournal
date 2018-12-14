> PG::ObjectInUse: ERROR: database "" is being accessed by other users DETAIL:  There is 1 other session using the database.

Solution:

This could be the rails server, rubymine and many more. Beside terminating the session connection manually you can also find out the pid and kill the process.

1. rails db
2. SELECT * FROM pg_stat_activity;
3. \q
4. sudo kill 21633.

		datid            | 98359
		datname          | foo_development
		pid              | 21633
		usesysid         | 16384
		usename          | username
		application_name | DataGrip 2017.2.1
		client_addr      | 127.0.0.1
		client_hostname  | [NULL]
		client_port      | 53682
		backend_start    | 2017-08-29 09:19:04.080051+02
		xact_start       | [NULL]
		query_start      | 2017-08-29 09:19:04.213843+02
		state_change     | 2017-08-29 09:19:04.213868+02
		waiting          | f
		state            | idle
		backend_xid      | [NULL]
		backend_xmin     | [NULL]
		query            | select current_database() as a, current_schemas(false) as b