# Active Record Query Interface

## Scopes

Scoping allows you to specify commonly-used queries which can be referenced as method calls on the association objects or models. With these scopes, you can use every method previously covered such as where, joins and includes. All scope methods will return an ActiveRecord::Relation object which will allow for further methods (such as other scopes) to be called on it.

To define a simple scope, we use the scope method inside the class, passing the query that we'd like to run when this scope is called:

	class Article < ActiveRecord::Base
	  scope :published, -> { where(published: true) }
	end

This is exactly the same as defining a class method, and which you use is a matter of personal preference:

	class Article < ActiveRecord::Base
	  def self.published
	    where(published: true)
	  end
	end









	














