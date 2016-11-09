# Editing User

	1 error prohibited this user from being saved:

	Password can't be blank

## Solutions Create Change Password facilty !

Create clone edit.html.erb named changepassword

	<% if params[:action] == "edit" %>
		...
		<div class="form-group">
		  <%= f.label :current_password %><br />
		  <%= f.password_field :current_password, autocomplete: "off" %>
		</div>

	<% elsif params[:action] == 'changepassword' %>
		...

	<% else %>

		...

Update routes.rb

	match "admin/users/:id/changepassword", to: "users#changepassword", via: :get

Create new file changepassword.html.erb

	paste edit.html.erb content	

Update form change password as below:

	<div class="form-group">
	  <%= f.label :password %><br />
	  <%= f.password_field :password, autocomplete: "off", class:'form-control' %>
	</div>

Give link for changepassword

	<a href="/admin/users/<%= user.id %>/changepassword">Change Password</a>		
