# Editing User

	1 error prohibited this user from being saved:

	Password can't be blank

## Solutions Create Change Password facility !

Create new file / clone edit.html.erb named changepassword.html.erb

![changepassw](http://res.cloudinary.com/medio/image/upload/v1484791412/changepasswordfile_uiu7yg.png)

Add password field on form:

	<div class="field">
      <%= f.label :password %>
      <% if @minimum_password_length %>
          <em>(<%= @minimum_password_length %> characters minimum)</em>
      <% end %><br />
      <%= f.password_field :password, autocomplete: "off", class:'form-control' %>
    </div>

    <div class="field">
      <%= f.label :password_confirmation %><br />
      <%= f.password_field :password_confirmation, autocomplete: "off", class:'form-control' %>
    </div>

Add Condition "params actions" in users form

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

Update the users controller

	def changepassword

	end	

Create new file changepassword.html.erb

	paste edit.html.erb content	

Update form change password as below:

	<div class="form-group">
	  <%= f.label :password %><br />
	  <%= f.password_field :password, autocomplete: "off", class:'form-control' %>
	</div>

Give link for changepassword

	<a href="/admin/users/<%= user.id %>/changepassword">Change Password</a>		
