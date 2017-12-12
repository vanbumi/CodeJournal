#### StandardError: An error has occurred, this and all later migrations canceled: Directly inheriting from ActiveRecord::Migration is not supported. Please specify the Rails release the migration was written for:

Solution: I change class RolifyCreateRoles < ActiveRecord::Migration to class RolifyCreateRoles < ActiveRecord::Migration[5.1]

