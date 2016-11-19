# Rollback & Destroy Migration

Using destroy scaffold does not run the rollback to the migration. The correct way of doing it would have been

	$ rake db:rollback

	$ rails destroy scaffold ...

now, as you don't have that other migration anymore, you cannot roll it back. You'll need to delete that table manually:

	$ rails dbconsole
	$ DROP TABLE ...;

Example:

	rails generate controller article
	# Oops!
	rails destroy controller article
	rails generate controller articles	

Also discovered you can “redo” the last migration as well, which is really handy as well for repairing mistakes:

	rake db:migrate:redo	

## Remove Field from table

	rails generate migration RemoveFieldNameFromTableName field_name:datatype

	rails g migration remove_category_from_posts category:string	