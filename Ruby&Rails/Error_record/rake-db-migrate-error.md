Rails Error: Unable to access log file. Please ensure that /home/dyo/sites/msweb/log/development.log exists and is writable

Solution:

	sudo touch /home/dyo/sites/msweb/log/development.log
	sudo chmod 0664 /home/dyo/sites/msweb/log/development.log
	
and

	sudo rake db:migrate
	
	
