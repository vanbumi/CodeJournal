# Rails Condition

## Controller Condition

Example for class

	class = "<%= params[:controller] == 'product' ? 'active' : '' %>"

## Create condition in Controller 

Example:

	def index
		if current_user.role == 'Master'
		  @users = User.all
		else
		  redirect_to '/dashboard'
		end
	end

Example 2

	if current_user.role.name == 'Master'
		  @users = User.all
    elsif current_user.role.name == 'Owner'
      @users = User.all  
	else
		  redirect_to '/admin/dashboard'
	end

Example 3:

	def index
	    if current_user.role.name == 'Master'
		  @users = User.all
		else
		  redirect_to '/admin/dashboard'
		end
	end	

## Conditional ('if') base on "Action"

The params hash that is available in the controller contains :controller and :action keys, which specify the controller and action names of the request.

### Therefore you could say

	if params[:action] == "foo"
	  # Show stuff for action 'foo'
	elsif params[:action] == "bar"
	  # Show stuff for action 'bar'
	elsif ...
	  # etc.
	end

## Example for my databaseck

### Case for query new form

	f.select :subbidang_id, Subbidang.where(:nama => 'PBL').collect {|x| [x.nama, x.id]}, {:include_blank => 'Isi'}, class:'form-control'

	<% if params[:action] == 'new' %>
	  <%= f.select :subbidang_id, Subbidang.where(:nama => 'PBL').collect {|x| [x.nama, x.id]}, {:include_blank => 'Isi'}, class:'form-control' %>
	<% elsif params[:action] == 'edit' %>
	  <%= f.select :subbidang_id, Subbidang.all.collect {|x| [x.nama, x.id]}, {:include_blank => 'Pilih'}, class:'form-control', :disabled => true %>
	  <% f.text_field :subbidang_id, class:'form-control' %>
	<% end %>

### Case for button

	<!--Button  -->
	<% if params[:action] == 'new' %>
	  <div class="actions">
	    <%= f.submit 'Add New', class:'btn btn-primary btn-xs' %>
	    <%= link_to 'Cancel', kuesioner_pbls_path, class:'btn btn-warning btn-xs' %>
	  </div>
	<% elsif params[:action] == 'edit' %>
	  <div class="actions">
	    <%= f.submit 'Update', class:'btn btn-primary btn-xs' %>
	    <%= link_to 'Cancel', kuesioner_pbls_path, class:'btn btn-warning btn-xs' %>
	  </div>
	<% end %>		

### Contoh penggunaannya pada User CRUD

	<% if params[:action] == "edit" %>

	  <!-- Edit Action -->
	  <%= form_for(user) do |f| %>
	    <% if user.errors.any? %>
	      <div id="error_explanation">
	        <h2><%= pluralize(user.errors.count, "error") %> prohibited this user from being saved:</h2>

	        <ul>
	        <% user.errors.full_messages.each do |message| %>
	          <li><%= message %></li>
	        <% end %>
	        </ul>
	      </div>
	    <% end %>

	    <div class="form-group">
	      <%= f.label :name %>
	      <%= f.text_field :name, class:'form-control' %>
	    </div>

	    <div class="form-group">
	      <%= f.label :email %>
	      <%= f.text_field :email, class:'form-control' %>
	    </div>

	    <div class="form-group">
	      <%= f.label :role_id %>
	      <%= f.select :role_id, Role.all.collect {|x| [x.name, x.id]}, {:include_blank => 'Pilih Role'}, class:'form-control' %>
	    </div>

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

	    <div class="actions">
	      <%= f.submit %>
	    </div>
	  <% end %>

	<% else %>

	  <!--- New Action -->
	  <%= form_for(user) do |f| %>
	    <% if user.errors.any? %>
	      <div id="error_explanation">
	        <h2><%= pluralize(user.errors.count, "error") %> prohibited this user from being saved:</h2>

	        <ul>
	        <% user.errors.full_messages.each do |message| %>
	          <li><%= message %></li>
	        <% end %>
	        </ul>
	      </div>
	    <% end %>

	    <div class="form-group">
	      <%= f.label :name %>
	      <%= f.text_field :name, class:'form-control' %>
	    </div>

	    <div class="form-group">
	      <%= f.label :email %>
	      <%= f.text_field :email, class:'form-control' %>
	    </div>

	    <div class="form-group">
	      <%= f.label :role_id %>
	      <%= f.select :role_id, Role.all.collect {|x| [x.name, x.id]}, {:include_blank => 'Pilih Role'}, class:'form-control' %>
	    </div>

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

	    <div class="actions">
	      <%= f.submit %>
	    </div>
	  <% end %>

	<% end %>


	



