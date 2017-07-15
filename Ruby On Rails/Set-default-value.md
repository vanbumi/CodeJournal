# Set default value with migration

	rails g migration SetDefaultValue

	def change
	    change_column :table_name, :column_name, :data_type, :default => "what ever"
	end

Example:

	class SetDefaultValue < ActiveRecord::Migration[5.0]
	  def change
	    change_column :products, :price_awal, :decimal, :default => 0
	  end
	end	