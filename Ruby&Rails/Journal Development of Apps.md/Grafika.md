# Grafika Steps

## Devise, Cancancan ...

#### Generate Controller Products for FrontEnd.

	rails g controller products index show

#### Generate Crud Products for BackEnd / Admin.

Create folder name admin, under app > controller

	rails g controller admin/products index show new create edit update destroy

#### Generate Controller for Category for FrontEnd.

	rails g controller categories index show	

#### And for Category admin / BackEnd.

	rails g controller admin/categories index show new create edit update destroy

#### Generate Controller About for FrontEnd

	rails g controller about index

#### Generate Controller Contact for FrontEnd

	rails g controller contacts new create

#### Generate Model for product

	rails g model product name:string category_id:integer description:text image:string price:decimal publish:string

#### Generate Model for category

	rails g model category name:string

#### Check model by rails console

	products = Product.all

add product

	products = Product.new(:name => 'Product One')
	products.save

and check result by

	products = Product.all



### Create Authontentication with Devise

	gem 'devise'

	bundle install

Configure the default URL options for development:

config/environments/development.rb

	[...]
	config.action_mailer.default_url_options = { host: '127.0.0.1', port: 3000 }
	[...]

This is required to properly generate links inside the e-mail views.

##### run the command to generate Devise’s configuration file and translations:

	$ rails generate devise:install

##### Next, generate a model with additional columns that are required by Devise:

	$ rails generate devise User

You may replace User with any other name. This command is going to create a user.rb model file and a migration that adds all the necessary fields. If the User model already exists, it will be updated.

##### Open up the model file to see what it contains. The most important line is:

models/user.rb

	[...]
	devise :database_authenticatable, :registerable,
	       :recoverable, :rememberable, :trackable, :validatable
	[...]


* database_authenticatable – Users will be able to authenticate with a login and password that are stored in the database. (password is stored in a form of a digest).
* registerable – Users will be able to register, update, and destroy their profiles.
* recoverable – Provides mechanism to reset forgotten passwords.
* rememberable – Enables “remember me” functionality that involves cookies.
* trackable – Tracks sign in count, timestamps, and IP address.
* validatable – Validates e-mail and password (custom validators can be used).

##### For this demo let’s also use two additional modules:

* confirmable – Users will have to confirm their e-mails after registration before being allowed to sign in.
* lockable – Users’ accounts will be locked out after a number of unsuccessful authentication attempts.

Modify the model like this:

user.rb

	[...]
	devise :database_authenticatable, :registerable,
	       :recoverable, :rememberable, :trackable, :validatable, :confirmable, :lockable
	[...]

##### You also have to edit the migration file, so open it up and uncomment the following lines:

db/migrations/xxx_devise_create_users.rb

	[...]
	t.string   :confirmation_token
	t.datetime :confirmed_at
	t.datetime :confirmation_sent_at
	t.string   :unconfirmed_email
	t.integer  :failed_attempts, default: 0, null: false
	t.string   :unlock_token
	t.datetime :locked_at
	add_index :users, :confirmation_token,   unique: true
	add_index :users, :unlock_token,         unique: true
	[...]

These fields are required for the Confirmable and Lockable modules to operate correctly. 

##### It is also a nice idea to allow users to provide their name, so add one more line:

db/migrations/xxx_devise_create_users.rb

	[...]
	t.string :name, 	null: false, default: ""
	[...]	

##### Now, run the migration:

	$ rake db:migrate

##### Generating Views

	rails generate devise:views

If you have more than one Devise model in your application (such as User and Admin), you will notice that Devise uses the same views for all models. Fortunately, Devise offers an easy way to customize views. All you need to do is set **config.scoped_views = true inside the config/initializers/devise.rb file**.

After doing so, you will be able to have views based on the role like users/sessions/new and admins/sessions/new. If no view is found within the scope, Devise will use the default view at devise/sessions/new. You can also use the generator to generate scoped views:

	$ rails generate devise:views users

##### Restart the server and view

http://localhost:3000/users/sign_in

http://localhost:3000/users/sign_up

##### Dont forget to create Menu Sign out like this:

	<ul class="nav navbar-nav pull-right">
        <% if user_signed_in? %>
          <li class="dropdown">
            <a class="dropdown-toggle" data-toggle="dropdown" href="#">
              <%= current_user.name %>
              <span class="caret"></span>
            </a>
            <ul class="dropdown-menu" role="menu">
              <li><%= link_to 'Profile', edit_user_registration_path %></li>
              <li><%= link_to 'Log out', destroy_user_session_path, method: :delete %></li>
            </ul>
          </li>
        <% else %>
          <li><%= link_to 'Log In', new_user_session_path %></li>
          <li><%= link_to 'Sign Up', new_user_registration_path %></li>
        <% end %>
	</ul>

##### Also create User CRUD

	$ rails g scaffold_controller User	

##### Strong_params and Edit Profile Page

Continue reading [here](https://www.sitepoint.com/devise-authentication-in-depth/)

### Authentication (Create Own)

##### Create Role

	rails g controller admin/roles index show new create edit update destroy

##### Add field Users model

	rails g migration add_role_id_to_users role_id:integer

##### Generate Model for Role

	rails g model role name:string

### Update routes.rb

Create resources for :

FrontEnd:

	resources :products, :categories
	resources "contacts", only: [:new, :create]  

BackEnd:

	namespace :admin do
		resources :products, :categories, :users, :roles
	end	 	

Update contact and etc, like below:

	get 'contact' => 'contacts#new'
	get 'about' => 'about#index'


### Setup the layout

##### Create admin layout views/layouts/admin

##### Copy & Paste conte views/layouts/application.html.erb to admin/application.html.erb

##### Create file application_controller.rb for controllers/admin & copas similar content into it. And add Admin::

	class Admin::ApplicationController < ActionController::Base
	  protect_from_forgery with: :exception
	end

##### Update all controller under admin folder as below:

	class Admin::CategoriesController < Admin::ApplicationController
	  def index
	end

##### Add Bootstrap CDN to Admin Layout or use existing from theme

##### Add dashboard controller

	 rails g controller admin/dashboard index
	 
##### Categories List order

	@categories = Category.all.order(:created_at => 'DESC')









	