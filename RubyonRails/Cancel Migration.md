# Rollback & Destroy Migration

Using destroy scaffold does not run the rollback to the migration. The correct way of doing it would have been

	$ rake db:rollback

	$ rails destroy scaffold level

now, as you don't have that other migration anymore, you cannot roll it back. You'll need to delete that table manually:

	$ rails dbconsole
	$ DROP TABLE levels;