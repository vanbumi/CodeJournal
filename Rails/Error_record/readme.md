### Error 1

Errno::EACCES in Home#index

Showing /home/dyo/sites/msweb/app/views/layouts/application.html.erb where line #7 raised:

Permission denied @ dir_s_mkdir - /home/dyo/sites/msweb/tmp/cache

SOLUTION:

	chmod 777 /home/dyo/sites/msweb/tmp/cache
	
	