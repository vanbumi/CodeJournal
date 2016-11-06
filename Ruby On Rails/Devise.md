# Devise authentication

## Getting started

Add Gemfile

	gem 'devise'

Run the bundle command to install it.

	$ bundle install

	$ bundle update

	$ rails g devise:install


Some setup you must do manually if you haven't yet:

	1. Ensure you have defined default url options in your environments files.

		Here is an example of default_url_options appropriate for a development	
		environment in config/environments/development.rb:
	
		config.action_mailer.default_url_options = { host: 'localhost', port: 3000 }
	
		In production, :host should be set to the actual host of your application.
	
	2. Ensure you have defined root_url to *something* in your config/routes.rb.
		For example:
		root to: "home#index"
	
	3. Ensure you have flash messages in app/views/layouts/application.html.erb.
	
		For example:
		<p class="notice"><%= notice %></p>
		<p class="alert"><%= alert %></p>
	
	4. If you are deploying on Heroku with Rails 3.2 only, you may want to set:
	
		config.assets.initialize_on_precompile = false
		On config/application.rb forcing your application to not access the DB or load
		models when precompiling your assets.
	
	5. You can copy Devise views (for customization) to your app by running:
		
		rails g devise:views		

Create table User

	$ rails g devise User

	$ rake db:migrate RAILS_ENV=development

Dont forget to refresh the server after this action!	

Check it out

	http://localhost:3000/users/sign_in

## Add sign_in, sign_out, and sign_up		

	<% if user_signed_in? %>
	  <li>
	  <%= link_to('Logout', destroy_user_session_path, :method => :delete) %>        
	  </li>
	<% else %>
	  <li>
	  <%= link_to('Login', new_user_session_path)  %>  
	  </li>
	<% end %>

Next come the sign_up links. Again, these can be substituted with something else useful if the user is already signed in:

	<% if user_signed_in? %>
	  <li>
	  <%= link_to('Edit registration', edit_user_registration_path) %>
	  </li>
	<% else %>
	  <li>
	  <%= link_to('Register', new_user_registration_path)  %>
	  </li>
	<% end %>

## Create Admin Limited Akses

	class AdminController < ApplicationController

	  before_action :authenticate_user!		

	  layout 'admin_layout'

	  def index
	  end
	end		

## Create Admin Page

	$ rails g scaffold_controller User

Change the Routes, add below:

	devise_for :users

  	resources :users, path: 'admin/users'

And add restriction 

	class UsersController < ApplicationController

	  before_action :authenticate_user!
	  before_action :set_user, only: [:show, :edit, :update, :destroy]  		

## Add User Role

### Adding an admin attribute

The easiest way of supporting an admin role is to simply add an attribute that can be used to identify administrators.

	$ rails generate migration add_admin_to_users admin:boolean

Add :default => false, to the line that adds the admin column to the table.

Your migration will now look like this:

	class AddAdminToUsers < ActiveRecord::Migration
	  def change
	    add_column :users, :admin, :boolean, :default => false
	  end
	end

Next, execute the migration script:

	$ rake db:migrate

Now you're able to identify administrators:

	if current_user.admin?
	  # do something
	end

If the page could potentially not have a current_user set then:

	if current_user.try(:admin?)
	  # do something
	end

With the above way if current_user were nil, then it would still work without raising an undefined method `admin?' for nil:NilClass exception.

The code below can be used to grant admin status to the current user.

	current_user.update_attribute :admin, true

In this case users tabel already have been made through Devise, we can still create admin page for tabel users with the following command:

	$ rails g scaffold_controller User

Next setup routers as following:

	Rails.application.routes.draw do	
		...
		devise_for :users
		resources :users, path: 'admin/users'
	end

You need to create name and attribut you want, like address etc

	rails g migration add_name_to_users name:string

## How To Change the default sign_in and sign_out routes
	
https://github.com/plataformatec/devise/wiki/How-To:-Change-the-default-sign_in-and-sign_out-routes
	
Open config/routes.rb and change as below:

	devise_for :users, :path => '...', :path_names => {:sign_in => 'new name', :sign_out => 'new name'}

### B Indonesia

Untuk membuat URL dengan path seperti /aut/sign_in, /aut/sign_out, dan URL default lainnya,
bukalah config/routes.rb dan tambahkan baris berikut:

	#devise_for dicomment agar default URL tidak dapat diakses
	#devise_for :users
	#ini URL devise yang baru
	
	devise_for :users, :path => 'aut'
	
Untuk mengganti berikut path_names, berikut codenya;
	
	devise_for :users, :path => 'aut', :path_names => {:sign_in => 'login', :sign_out
	=> 'logout'}

example

	devise_for :users, :path => 'newpath', :path_names => {:sign_in => 'newname', :sign_up => 'newname', :sign_out => 'newname'}	

Sehingga URLnya sekarang menjadi /aut/login, /aut/logout beberapa URL default lainnya yang
diawali dengan path /aut.	

## Create custom layouts

	https://github.com/plataformatec/devise/wiki/How-To:-Create-custom-layouts	

## Remove Forgot Password modules/links

Also do the changes in devise/shared/_link.html.erb by deleting the path generation links of sign_up and forgot_password

## Disable registration

In Devise model user.rb remove the devise :registerable, :recoverable option.

## Custom user delete in Devise

[custom-user-delete-in-devise](http://liquidmedia.org/blog/2011/08/custom-user-delete-in-devise/)

## Error

When logout 

	No route matches [GET] "/users/sign_out"

Solution

Modify config/initializer/devise.rb to

	config.sign_out_via = :get

And change the link

	<%= link_to "log out", destroy_user_session_path, method: :get %>


## User New, Edit & Update

	1 error prohibited this user from being saved, Password can't be blank

#### Solution:

You need add unpermitted params to

	def user_params
	  params.require(:user).permit(:name, :email, :password, :password_confirmation)
	end

You need add current_password

	<div class="field">
	    <% f.label :password %>
	    <% if @minimum_password_length %>
	        <em>(<%= @minimum_password_length %> characters minimum)</em>
	    <% end %><br />
	    <% f.password_field :password, autocomplete: "off" %>
	    <% f.password_field :current_password, autocomplete: "off" %>
	  </div>

	  <div class="field">
	    <% f.label :password_confirmation %><br />
	    <% f.password_field :password_confirmation, autocomplete: "off" %>
	    <% f.password_field :current_password, autocomplete: "off" %>
	  </div>	

		....


You need create if conditon base on controller action :

	if params[:action] == "foo"
	  # Show stuff for action 'foo'
	elsif params[:action] == "bar"
	  # Show stuff for action 'bar'
	elsif ...
	  # etc.
	end

