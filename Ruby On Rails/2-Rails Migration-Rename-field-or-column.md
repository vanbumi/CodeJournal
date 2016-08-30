## How can I rename a database column in a Ruby on Rails migration?

## An update for Rails 4

While creating a Migration as for renaming a column, Rails 4 generates a change method instead of up and down as mentioned in the above answer. The generated change method is as below :

	$ rails g migration ChangeColumnName

which will create a migration file similar to this :

	class ChangeColumnName < ActiveRecord::Migration
	  def change
	    rename_column :table_name, :old_column, :new_column
	  end
	end

## Rails Migrations to Add a Column and Change Column Type
	
Reference:

	https://codequizzes.wordpress.com/2013/06/06/rails-migrations-to-add-a-column-and-change-column-type/#comments

Suppose we have a Post model with body:integer and title:string columns. Generate a migration to add a user_id column to the posts table.

	$ rails g migration AddUserIdToPosts
	
Update the migration file, so the $ rake db:migrate command will add the user_id column to the posts table.

	class AddUserIdToPosts < ActiveRecord::Migration
	  def change
	    add_column :posts, :user_id, :integer
	  end
	end

The change method automatically lets us run the migration and roll it back, so all of the following commands will execute as expected:

	$ rake db:migrate
	$ rake db:rollback
	$ rake db:migrate

Lets add another migration to change the type of the body column to be text instead of an integer.

	$ rails g migration ChangeBodyTypeInPosts
	
	class ChangeBodyTypeInPosts < ActiveRecord::Migration
	  def change
	    change_column :posts, :body, :text
	  end
	end
	
If we run this migration and check the schema file, we will see that it was successful in changing the type of the body column to text. However, this migration is flawed because a rollback is not allowed:

	$ rake db:rollback
	==  ChangeBodyTypeInPosts: reverting ==========================================
	rake aborted!
	An error has occurred, this and all later migrations canceled:
	 
	ActiveRecord::IrreversibleMigration
	Tasks: TOP => db:rollback
	(See full trace by running task with --trace)
	
Some migrations are meant to raise an ActiveRecord::IrreversibleMigration exception, but this is the type of migration where that is probably not true. Here is a better way to create the migration:

	class ChangeBodyTypeInPosts < ActiveRecord::Migration
	  def self.up
	    change_column :posts, :body, :text
	  end
	 
	  def self.down
	    change_column :posts, :body, :integer
	  end
	end

When the up and down methods are specifically defined, migrations and rollbacks both function properly. This leads to a more general point: whenever you create a migration, check to make sure it can be rolled back and migrated successfully.	

## Error migration because of mistaken or typo, can not do rake db:migrate

![error migration](http://res.cloudinary.com/medio/image/upload/v1472528990/error_migration_vqznez.png)

	What I did go to database and delete that field manualy
	and 
	do rake db:migrate


