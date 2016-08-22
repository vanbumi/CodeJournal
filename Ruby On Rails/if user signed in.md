## If user signed in

	<% if user_signed_in? %>
	  <h1 id="welcome" class="nuvo">Welcome <%= current_user.username %>!</h1>
	<% else %>
	  <h1 id="welcome" class="nuvo">Log-In to make some posts!</h1>
	<% end%>

## Display Name

	<% if user_signed_in? %>
	    <% if current_user.name.blank? %>              
	      <h1>Welcome <strong><%= current_user.email %></strong>
	    <% else %> 
	      <h1>Welcome <strong><%= current_user.name %></strong>
	    <% end %>
	    <small>You Look Awesome!</small></h1>  
  	<% end %>	