# Current User Photo

## index.html.erb

	<% if current_user.photos.present? %>
	  <% @users.each do |current_user| %>
	      <% current_user.photos.each do |photo| %>
	          <%= cl_image_tag(photo.path, { size: '30x30', crop: :thumb }) %>
	      <% end %>
	  <% end %>
	<% else %>
	  <%= image_tag("user.jpg", size: "30x30", alt: "default-photo") %>
	<% end %>

## Use this right one!

	<% if current_user.avatar.present? %>
    	<%= cl_image_tag(current_user.avatar.path, size: '30x30', crop: :thumb) %>
	<% else %>
	  <img src="http://res.cloudinary.com/medio/image/upload/c_scale,h_30,w_30/v1477035785/user_r8zlsq.jpg" alt="" class="img-responsive">
	<% end %>	