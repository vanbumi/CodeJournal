# many to many rails

. [create-a-many-to-many-activerecord-association-in-ruby-on-rails](http://joshfrankel.me/blog/2016/how-to/create-a-many-to-many-activerecord-association-in-ruby-on-rails/){:target = "_blank"}

**Question**:

	and how to show them, such like programmer.name or project name in view?

**Answer**

	If you wanted to use programmer.name or project.name within a view you first would need a controller that contained an instance variable set to whatever model you were looking to use. Also a proper route to use it. I've written a contrived example below of what I mean.

		# file: app/controllers/programmers_controller.rb
		class ProgrammersController < ActionController::Base
		  
		  def index # or another action name
		    @programmers = Programmer.all # Use activerecord to query for all programmers
		  end
		  
		  # more actions
		end

		# file: config/routes.rb
		resources :programmers, only: :index

		# file: app/views/programmers/index.html.erb
		# Some quick code that will show programmer's names in a view
		<% @programmers.each do |programmer| %>
			<%= programmer.name %>
		  
			<% programmer.projects.each do |project| %>
		   		<%= project.name %>
			<% end %>
		<% end %>			

. [master-many-to-many-associations-with-activerecord](https://www.sitepoint.com/master-many-to-many-associations-with-activerecord/){:target = "_blank"}

. [Has-Many-Through-and-Has-and-Belongs-to-Many-in-Rails-5](https://www.rubyplus.com/articles/3451-Has-Many-Through-and-Has-and-Belongs-to-Many-in-Rails-5){:target = "_blank"} -> uncomplete tutorial.

. [rails-many-to-many](https://github.com/sf-wdi-gaia/rails-many-to-many){:target = "_blank"}

. Menjelaskan sedikit tentang show to view: [How-to-model-a-many-to-many-relationship-in-rails](http://toranbillups.com/blog/archive/2010/09/09/How-to-model-a-many-to-many-relationship-in-rails/)

. http://www.xyzpub.com/en/ruby-on-rails/3.2/ar-many_to_many.html

. http://brandonclapp.com/many-to-many-model-relationships-in-rails/

. https://blog.coryfoy.com/2008/02/multiselect-control-in-rails-with-a-many-to-many-relationship/

. http://www.createdbypete.com/articles/working-with-nested-forms-and-a-many-to-many-association-in-rails-4/
