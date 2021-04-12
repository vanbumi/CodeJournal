## Error known

After clone / different ruby version:

	rbenv: version `ruby-2.1.2' is not installed
	(set by /home/dyo/sites_lat/filterrific_demo/.ruby-version)
		
Solution:

Trying this [Rbenv: version `2.1.3’ is not installed when trying to install exercise](https://forum.upcase.com/t/rbenv-version-2-1-3-is-not-installed-when-trying-to-install-exercise/3039). Succed 

	rbenv install 2.1.2


Another error 

	rbenv: rails: command not found

Tried :

	gem install rails

Error :

	ERROR:  Error installing rails:
	activesupport requires Ruby version >= 2.2.2.

I tried this:

	gem install rails -v 4.2.2

Succed

Error again: Your Ruby version is 1.9.3, but your Gemfile specified 2.1.2

Solution:

I have tried:

	gem install bundler

	does not work

Error again: Could not find rake-11.2.2 in any of the sources

Error again: 

PG::UndefinedFile: ERROR:  could not open extension control file "/usr/share/postgresql/9.3/extension/hstore.control": No such file or directory	

Solution: 

	sudo apt-get install postgresql-contrib-9.3

Error:

	E: Unable to locate package postgresql-contrib-9.3.3
	E: Couldn't find any package by regex 'postgresql-contrib-9.3.3'

Solution:

	 apt-get update

Problem is **hstore** Solution here:

[Enabling hstore](https://gist.github.com/terryjray/3296171)

Error rake db:migrate

NameError: uninitialized constant ChangeColumnTypeOfWeightOnProducts::Product
/home/dyo/sites/ukmmarket/db/migrate/20150210011556_change_column_type_of_weight_on_products.rb:4:in `change'

Solution:




