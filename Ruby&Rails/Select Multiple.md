# Multiple Select

**Standard HTML**

	<div class="form-group">
	    <label class="col-md-3 control-label" for="example-text-input"><%= f.label :multiple %></label>
	    <div class="col-md-9">
	      <%= f.select(:PartisipasiSwasta, [['Type A', 'Type A'],
	                                        ['Type B', 'Type B'],
	                                        ['Type C', 'Type C'],
	                                        ['Type D', 'Type D'],
	                                        ['Type E', 'Type E']
	      ],{ :prompt => "Please select"},
	                   { :multiple => true, :size => 5, class:'form-control' }
	          ) %>
	      <br>
	    </div>
	</div>

**Rails**

	<%= f.select :category_id, Category.all.collect {|x| [x.name, x.id]}, 
	  { :prompt => "Please select"},
	  { :multiple => true, :size => 5, class:'form-control' }  
	%>

**how to save multiple values from multiple select to database rails**

+ finaly got answered he said: http://stackoverflow.com/questions/20968665/
select-with-multiple-true-not-saving-values

		class ChangeAvailableTypeOnTerminals < ActiveRecord::Migration
		  def up
		    change_column :terminals, :available_type, :text, array: true, default: []
		  end

		def down
		    change_column :terminals, :available_type, :string
		  end
		end

+ http://stackoverflow.com/questions/29392314/how-save-multiselect-values-to-database

	Migration:

		rails g migration change_order_type_in_table_name

		class ChangeOrderTypeInTableName < ActiveRecord::Migration
		  def up
		    change_column :my_table, :order, :text
		  end

		  def down
		    change_column :my_table, :order, :string
		  end
		end

	Serialize:

		You can pass a class to serialize:

		  class User < ActiveRecord::Base
		      serialize :order, Array
		    end
		    The above ensures that order as an Array:

##### My conclusion about this migration:

	$ rails g migration ChangeBodyTypeInPosts

	class ChangeBodyTypeInPosts < ActiveRecord::Migration
	  def self.up
	    change_column :posts, :body, :text
	  end

	  def self.down
	    change_column :posts, :body, :integer
	  end
	end		    

	body  => name of column
	posts => name of table

+ **Dearmom case**

**do serialize**

**do change type integer to string**

		rails g migration ChangeCategory_idTypeInBrands

	produce this:		

		class ChangeCategoryIdTypeInBrands < ActiveRecord::Migration[5.0]
		  def change
		  end
		end

	Add this:
	
		def self.up
	    change_column :brands, :category_id, :text
	  end

	  def self.down
	    change_column :brands, :category_id, :integer
	  end

Error Produced:

		SyntaxError: /home/dyo/sites/rails/babyshop-2/db/migrate/20170427121810_change_category_id_type_in_
		brands.rb:3: syntax error, unexpected keyword_def, expecting ']'
		  def self.up	  	

	Problem it was: 

		class ChangeCategoryIdTypeInBrands < ActiveRecord::Migration[5.0 
	
	Solutions

		add ]

	and
		
		def up
	    change_table :brands do |t|
	      t.change :category_id, :text
	    end
	  end
	 
	  def down
	    change_table :brands do |t|
	      t.change :category_id, :integer
	    end
	  end	  
