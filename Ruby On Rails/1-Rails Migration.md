# Rails Migration

## Rails Migration Generate, Add, Remove etc

### Add Column

	$ rails generate migration AddPartNumberToProducts part_number:string

will generate

	class AddPartNumberToProducts < ActiveRecord::Migration[5.0]
	  def change
	    add_column :products, :part_number, :string
	  end
	end

### Add an index on the new column

	$ rails generate migration AddPartNumberToProducts part_number:string:index

will generate

	class AddPartNumberToProducts < ActiveRecord::Migration[5.0]
	  def change
	    add_column :products, :part_number, :string
	    add_index :products, :part_number
	  end
	end

### Remove a column

	$ rails generate migration RemovePartNumberFromProducts part_number:string

generates

	class RemovePartNumberFromProducts < ActiveRecord::Migration[5.0]
	  def change
	    remove_column :products, :part_number, :string
	  end
	end	

### Add Multi Column

You are not limited to one magically generated column. For example:

	$ rails generate migration AddDetailsToProducts part_number:string price:decimal
	
generates

	class AddDetailsToProducts < ActiveRecord::Migration[5.0]
	  def change
	    add_column :products, :part_number, :string
	    add_column :products, :price, :decimal
	  end
	end

Sample rumit:

	rails generate migration AddDetailsToKuesionerPbl RumahTinggalTunggal:integer RumahTinggalTunggalBerImb:integer RumahTinggalDeret:integer RumahTinggalDeretBerImb:integer RumahTinggalSusun:integer RumahTinggalSusunBerImb:integer RumahTinggalSementara:integer	

### Create Table

If the migration name is of the form "CreateXXX" and is followed by a list of column names and types, then a migration creating the table XXX with the columns listed will be generated. For example:

	$ rails generate migration CreateProducts name:string part_number:string

generates

	class CreateProducts < ActiveRecord::Migration[5.0]
	  def change
	    create_table :products do |t|
	      t.string :name
	      t.string :part_number
	    end
	  end
	end

### Add references  

The generator accepts column type as references(also available as belongs_to). For instance:

	$ rails generate migration AddUserRefToProducts user:references

generates

	class AddUserRefToProducts < ActiveRecord::Migration[5.0]
	  def change
	    add_reference :products, :user, foreign_key: true
	  end
	end

This migration will create a **user_id** column and appropriate index. For more add_reference options, visit the [API documentation.](http://api.rubyonrails.org/classes/ActiveRecord/ConnectionAdapters/SchemaStatements.html#method-i-add_reference)

### Add join tables, by **JoinTable**

	$ rails g migration CreateJoinTableCustomerProduct customer product

will produce the following migration:

	class CreateJoinTableCustomerProduct < ActiveRecord::Migration[5.0]
	  def change
	    create_join_table :customers, :products do |t|
	      # t.index [:customer_id, :product_id]
	      # t.index [:product_id, :customer_id]
	    end
	  end
	end

Sources: [Active Record Migrations](http://edgeguides.rubyonrails.org/active_record_migrations.html)

## Stack overflow

### Change data type

	rails g migration change_data_type_for_peta_drainase

Then edit the migration to use change_table:

class ChangeDataTypeForPetaDrainase < ActiveRecord::Migration
  def self.up
    change_table :drainases do |t|
      t.change :peta_drainase, :string
    end
  end
  def self.down
    change_table :tablename do |t|
      t.change :peta_drainase, :boolean
    end
  end
end

Then run the migration:

rake db:migrate	