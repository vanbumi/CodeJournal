## Module: Devise::Models::Authenticatable

[Module: Devise::Models::Authenticatable](http://www.rubydoc.info/github/plataformatec/devise/master/Devise/Models/Authenticatable)

### Overview

Authenticatable module. Holds common settings for authentication.

### Options

Authenticatable adds the following options to devise_for:

* +authentication_keys+: parameters used for authentication. By default [:email].

* +http_authentication_key+: map the username passed via HTTP Auth to this parameter. Defaults to the first element in +authentication_keys+.

* +request_keys+: parameters from the request object used for authentication.
  By specifying a symbol (which should be a request method), it will automatically be
  passed to find_for_authentication method and considered in your model lookup.
  For instance, if you set :request_keys to [:subdomain], :subdomain will be considered
  as key on authentication. This can also be a hash where the value is a boolean specifying
  if the value is required or not.

* +http_authenticatable+: if this model allows http authentication. By default false.
  It also accepts an array specifying the strategies that should allow http.

* +params_authenticatable+: if this model allows authentication through request params. By default true. It also accepts an array specifying the strategies that should allow params authentication.

* +skip_session_storage+: By default Devise will store the user in session.
  By default is set to skip_session_storage: [:http_auth].

**active_for_authentication?**

After authenticating a user and in each request, Devise checks if your model is active by calling model.active_for_authentication?. This method is overwritten by other devise modules. For instance, :confirmable overwrites .active_for_authentication? to only return true if your model was confirmed.

You can overwrite this method yourself, but if you do, don't forget to call super:

	def active_for_authentication?
	  super && special_condition_is_valid?
	end

Whenever active_for_authentication? returns false, Devise asks the reason why your model is inactive using the inactive_message method. You can overwrite it as well:

	def inactive_message
	  special_condition_is_valid? ? super : :special_condition_is_not_valid
	end	  

**Penjelasan**

[Click here](https://github.com/plataformatec/devise/wiki/How-To%3a-Customize-user-account-status-validation-when-logging-in)	or write as bellow:

	def active_for_authentication?
	    super && account_active?
	end

	def inactive_message
	  account_active? ? super : :anda_sementara_tidak_boleh_login
	end	

[Stack Overflow](http://stackoverflow.com/questions/6004216/devise-how-do-i-forbid-certain-users-from-signing-in)

Make sure you have flash setup in the view, something like.
[devise-inactive-message-wont-display](http://stackoverflow.com/questions/31461284/devise-inactive-message-wont-display)

	/views/layouts/application.html.erb

	<% flash.each do |name, msg| %>
	  <%= content_tag(:div, msg, class: "alert alert-#{name}") %>
	<% end %>	  

## The steps

Add Column account_active

	rals g migration AddAccountActiveOnUsers account_active:boolean
	set default as true

On your model user.rb

	def active_for_authentication?
		super && account_active?
	end

	def inactive_message
		'Anda sementara tidak boleh login'
	end

On your devise login page, views/devise/sessions/new.html.erb

	<% flash.each do |name, msg| %>
	    <div class="alert alert-danger text-center">
	      <%= msg %>
	    </div>
	<% end %>

Done!