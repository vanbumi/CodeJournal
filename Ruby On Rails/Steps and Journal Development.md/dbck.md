# Database CK

## Change db from postgresql -> mysql

* Doing clone for backup & safety

* Update Gemfile

* Update database.yml

* Error 

	dyo@dyo-medio:~/sites/dbck_mysql$ rake db:create
	rake aborted!
	Gem::LoadError: You have already activated rake 11.3.0, but your Gemfile requires rake 11.2.2. Prepending `bundle exec` to your command may solve this.
	/home/dyo/sites/dbck_mysql/config/boot.rb:3:in `<top (required)>'
	/home/dyo/sites/dbck_mysql/config/application.rb:1:in `<top (required)>'
	/home/dyo/sites/dbck_mysql/Rakefile:4:in `<top (required)>'
	LoadError: cannot load such file -- bundler/setup
	/home/dyo/sites/dbck_mysql/config/boot.rb:3:in `<top (required)>'
	/home/dyo/sites/dbck_mysql/config/application.rb:1:in `<top (required)>'
	/home/dyo/sites/dbck_mysql/Rakefile:4:in `<top (required)>'
	(See full trace by running task with --trace)

	Solution: bundle exec rake db:create

	Specified 'mysql2' for database adapter, but the gem is not loaded. Add `gem 'mysql2'` to your Gemfile (and ensure its version is at the minimum required by ActiveRecord).

	Solution: gem 'mysql2', '~> 0.3.13'

	dyo@dyo-medio:~/sites/dbck_mysql$ bundle exec rake db:migrate
	== 20160815103716 DeviseCreateUsers: migrating ================================
	-- create_table(:users)
	rake aborted!
	StandardError: An error has occurred, all later migrations canceled:

	undefined method `inet' for #<ActiveRecord::ConnectionAdapters::TableDefinition:0xb95a1900>
	/home/dyo/sites/dbck_mysql/db/migrate/20160815103716_devise_create_users.rb:19:in `block in change'
	/home/dyo/sites/dbck_mysql/db/migrate/20160815103716_devise_create_users.rb:3:in `change'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `load'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `<main>'
	NoMethodError: undefined method `inet' for #<ActiveRecord::ConnectionAdapters::TableDefinition:0xb95a1900>
	/home/dyo/sites/dbck_mysql/db/migrate/20160815103716_devise_create_users.rb:19:in `block in change'
	/home/dyo/sites/dbck_mysql/db/migrate/20160815103716_devise_create_users.rb:3:in `change'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `load'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `<main>'
	Tasks: TOP => db:migrate
	(See full trace by running task with --trace)

	Solution:

	You can replace it with "string" type and it will work

	# pg
	# t.inet     :current_sign_in_ip
	# t.inet     :last_sign_in_ip

	# mysql
	t.string     :current_sign_in_ip
	t.string     :last_sign_in_ip

	bundle exec rake db:migrate
	== 20160901075930 AddNamaInsDrainsToDrainases: migrating ======================
	-- add_column(:drainases, :nama_ins_drains, :string)
	rake aborted!
	StandardError: An error has occurred, all later migrations canceled:

	Mysql2::Error: Row size too large. The maximum row size for the used table type, not counting BLOBs, is 65535. You have to change some columns to TEXT or BLOBs: ALTER TABLE `drainases` ADD `nama_ins_drains` varchar(255)
	/home/dyo/sites/dbck_mysql/db/migrate/20160901075930_add_nama_ins_drains_to_drainases.rb:3:in `change'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `load'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `<main>'
	ActiveRecord::StatementInvalid: Mysql2::Error: Row size too large. The maximum row size for the used table type, not counting BLOBs, is 65535. You have to change some columns to TEXT or BLOBs: ALTER TABLE `drainases` ADD `nama_ins_drains` varchar(255)
	/home/dyo/sites/dbck_mysql/db/migrate/20160901075930_add_nama_ins_drains_to_drainases.rb:3:in `change'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `load'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `<main>'
	Mysql2::Error: Row size too large. The maximum row size for the used table type, not counting BLOBs, is 65535. You have to change some columns to TEXT or BLOBs
	/home/dyo/sites/dbck_mysql/db/migrate/20160901075930_add_nama_ins_drains_to_drainases.rb:3:in `change'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `load'
	/home/dyo/.rbenv/versions/2.3.1/bin/bundle:23:in `<main>'
	Tasks: TOP => db:migrate
	(See full trace by running task with --trace)

	Solution: I delete all shit migration on db > migrate file 



