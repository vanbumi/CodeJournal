# All about current_user

## Create Link to Profile Current User

	<li>
		<a href="/admin/users/<%= current_user.id %>">Profile</a>
	</li>

## Dropdown top navigation

	<li class="dropdown">
	  <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">
	    <% if current_user.avatar.present? %>
	      	<%= cl_image_tag(current_user.avatar.path, size: '25x25', crop: :thumb, class:'img-circle') %>
	  	<% else %>
	  	  <img src="http://res.cloudinary.com/medio/image/upload/c_scale,h_25,w_25/v1477035785/user_r8zlsq.jpg" alt="" class="img-responsive">
	  	<% end %>
	    <%= current_user.role.name %>
	    <span class="caret"></span></a>
	  <ul class="dropdown-menu">
	    <li><a href="/admin/users/<%= current_user.id %>">Profil Ku</a></li>
	    <li><a href="#">Another action</a></li>
	    <li><a href="#">Something else here</a></li>
	    <li role="separator" class="divider"></li>
	    <% if user_signed_in? %>
	      <li>
	      <%= link_to('Logout', destroy_user_session_path, :method => :delete) %>
	      </li>
	    <% else %>
	      <li>
	      <%= link_to('Login', new_user_session_path)  %>
	      </li>
	    <% end %>
	  </ul>
	</li>	
