

	rails new api_perfecto_apiapp --api

	cd  <parent-folder-path>/api_app_name
	bundle install
	bin/rake db:setup

Using RSpec for Testing

let’s setup RSpec for spec testing our application. The reason it’s good to setup RSpec first that we can save a bit of time using the built-in RSpec generators to auto generate default model and controller specs for us each time we use rails generate scaffold to generate resources later on. 

To install RSpec, go ahead and add the rspec-rails gem to your Gemfile in the **:development, :test group:**

	group :development, :test do

	  # Use RSpec for specs
	  gem 'rspec-rails', '>= 3.5.0'

	  # Use Factory Girl for generating random test data
	  gem 'factory_girl_rails'
	end

	bundle install

Run the RSpec installer:

	bin/rails g rspec:install

Finally, you can get rid of the test directory in Rails, since we won’t be writing unit tests, but writing specifications instead.

### Bulding Your API

Lets building out API controllers.

When an app is created with the --api flag you can use the default scaffold generators to generate your API resources as normal, without the need for any special arguments.

	bin/rails g scaffold user name email

This will generate the following file structure:	

	invoke  active_record
	create    db/migrate/20161206092654_create_users.rb
	create    app/models/user.rb
	invoke    rspec
	create      spec/models/user_spec.rb
	invoke      factory_girl
	create        spec/factories/users.rb
	invoke  resource_route
	route    resources :users
	invoke  scaffold_controller
	create    app/controllers/users_controller.rb
	invoke    rspec
	create      spec/controllers/users_controller_spec.rb
	create      spec/routing/users_routing_spec.rb
	invoke      rspec
	create        spec/requests/users_spec.rb

Note that no views are created since we are running in API mode.

Go ahead and repeat the process with as many resources as you like, and once you’re done you can migrate and run the app:

	bin/rake db:migrate

	# run the default server on port 3000
	bin/rails s

Your new API is now up and running on http://localhost:3000. Sweet!

You’re not done yet though, there are still a bunch of important points for consideration…

### Serializing API Output

In it’s current state our app will just spit out a JSON representation of every column in the database so we need a way to control what data gets served through the API.

Normally we would use a front end **templating engine such as jbuilder** for this purpose, but since we’re not using views in our **super streamlined API app**, that’s not going to be an option.

Fortunately AMS (**Active Model Serializers**) is here to save the day. AMS provides a clean layer between the model and the controller that lets us to call **to_json** or **as_json** on the ActiveRecord object or collection as normal, while outputing our desired API format.

add the active_model_serializers gem to your Gemfile:

	gem 'active_model_serializers'

Update your bundle:

	bundle

Now lets create a default serializer for our User model:

	rails g serializer user

It will generate

	Expected string default value for '--serializer'; got true (boolean)
      create  app/serializers/user_serializer.rb

In app/serializers/user_serializer.rb, we find this code:

	class UserSerializer < ActiveModel::Serializer
	  attributes :id
	end

Note that only the :id attribute is added by default. That’s not going to be much use to us, so go ahead and add the **:name and :email attributes** to the serializer:

	class UserSerializer < ActiveModel::Serializer
	  attributes :id, :name, :email
	end

> If your model has relationships just declare them on the serializer as you would any other attributes to be serialized in the output.

You also need to include the ActionController::Serialization dependency in your controller like so:

class ApplicationController < ActionController::API
  include ActionController::Serialization

  # ...
end

Now when you hit and User related API endpoint only the attributes in the UserSerializer will be rendered. Nice!

Check the [active_model_serializers](https://github.com/rails-api/active_model_serializers) gem homepage for more detailed configuration options.

### Enabling CORS

If you’re building a public API you’ll probably want to **enable Cross-Origin Resource Sharing (CORS)**, in order to make **cross-origin AJAX requests possible**.

This is made very simple by the **rack-cors gem**. Just stick it in your Gemfile like so:

	gem 'rack-cors'

Update your bundle:

	bundle

And put something like the code below in **config/application.rb** of your Rails application. For example, this will allow **GET**, **POST** or **OPTIONS** requests from any origin on any resource.

	module YourApp
	  class Application < Rails::Application

	    # ...

	    config.middleware.insert_before 0, "Rack::Cors" do
	      allow do
	        origins '*'
	        resource '*', :headers => :any, :methods => [:get, :post, :options]
	      end
	    end

	  end
	end

For more detailed configuration options please see the gem documentation: https://github.com/cyu/rack-cors

### Versioning Your API

Before releasing your public API into the wild, you should consider implementing some form of versioning. Versioning breaks your API up into multiple version namespaces, such as v1 and v2, so that you can maintain backwards compatibility for existing clients whenever you introduce breaking changes into your API, simply by incrementing your API version.

**This guide will show you how to setup versioning with the following URL format**:

	GET http://api.mysite.com/v1/users/

Using a subdomain instead of something like /api/v1/users/ **is just a preference**, although both are easy to accomplish in Rails.

We can use a directory structure like this to keep our **controller** code clean by defining all our v1 controllers within the **Api::V1 namespace:**

	app/controllers/
	.
	|-- api
	|   `-- v1
	|       |-- api_controller.rb
	|       `-- users_controller.rb
	|-- application_controller.rb

Here’s what the controllers look like:

	# app/controllers/api/v1/api_controller.rb

	module Api::V1
	  class ApiController < ApplicationController
	    # Generic API stuff here
	  end
	end


	# app/controllers/api/v1/users_controller.rb

	module Api::V1
	  class UsersController < ApiController

	    # GET /v1/users
	    def index
	      render json: User.all
	    end

	  end
	end

Now let’s setup our config/routes.rb to tie everything together:

	constraints subdomain: 'api' do
	  scope module: 'api' do
	    namespace :v1 do
	      resources :users
	    end
	  end
	end

The scope module: 'api' bit lets us route to controllers in the API module without explicitly including it in the URL. However, the version v1/ is part of the URL, and we also want to route to the V1 module, so we use namespace.

Now you’re API routes are looking pretty sharp!

### Rate Limiting and Throttling

To protect our API from DDoS, brute force attacks, hammering, or even to monetize with paid usage limits, we can use a **Rake middleware** called **Rack::Attack**. The rack-attack gem was released by Kickstarter, and it allows us to:

* whitelist: Allowing it to process normally if certain conditions are true
* blacklist: Sending a denied message instantly for certain requests
* throttle: Checking if the user is within their allowed usage
* track: Tracking this request to be able to log certain information about our requests

Get started by adding the dependency to your Gemfile:

	gem 'rack-attack'	