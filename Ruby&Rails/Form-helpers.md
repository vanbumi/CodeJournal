# Form Helpers

## Basic Forms

	<%= form_tag do %>
		Form contents
	<% end %>

## Form scaffold

	<%= form_for(@user) do |f| %>
	  <% if @user.errors.any? %>
	    <div id="error_explanation">
	      <h2><%= pluralize(@user.errors.count, "error") %> prohibited this user from being saved:</h2>

	      <ul>
	      <% @user.errors.full_messages.each do |message| %>
	        <li><%= message %></li>
	      <% end %>
	      </ul>
	    </div>
	  <% end %>

	  <div class="field">
	    <%= f.label :name %><br>
	    <%= f.text_field :name, class:"form-control" %>
	  </div>

	  <div class="field">
	    <%= f.label :email %><br>
	    <%= f.text_field :email, class:"form-control" %>
	  </div>
	  
	  <div class="actions">
	    <%= f.submit %>
	  </div>
	<% end %>

## Show Scaffold

	<p id="notice"><%= notice %></p>

	<p>
	  <strong>Name:</strong>
	  <h3><%= @user.name %></h3>
	</p>

	<p>
	  <strong>Description:</strong>
	  <%= @user.email %>
	</p>

	<%= link_to 'Edit', edit_user_path(@user) %> |
	<%= link_to 'Back', users_path %>