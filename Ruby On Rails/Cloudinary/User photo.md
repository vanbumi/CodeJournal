## To show photo on View Index

	<% @users.each do |user| %>
	  <% user.photos.each do |photo| %>
	      <%= cl_image_tag(photo.path, {
	          :width => 60, :height => 60, :crop => :thumb,
	          :gravity => false, :radius => 'max' }) %>
	  <% end %>
	<% end %>

## To show photo on View Show

	<%= cl_image_tag(photo.path,
       :width => 200, :height => 200,
       :crop => :thumb, :gravity => :face, :radius => 'max'
   	) %>

## If condition, I put in Edit

	<div class="form-group">
      <% if @user.avatar? %>
        <%= cl_image_tag @user.avatar.path, :width => 100, :height => 100, :crop => :thumb, class:'img-thumbnail' %>
      <% else %>
          <img src="http://res.cloudinary.com/medio/image/upload/c_scale,h_100,w_100/v1477035785/user_r8zlsq.jpg" alt="" class="img-responsive">
      <% end %>
    </div>

#### I put in Show

	  <% if @user.avatar? %>
      <%= cl_image_tag @user.avatar.path, :width => 250, :height => 250, :crop => :thumb, :gravity => :face %>
    <% else %>
        <img src="http://res.cloudinary.com/medio/image/upload/c_scale,h_250,w_250/v1477035785/user_r8zlsq.jpg" alt="" class="img-responsive">
    <% end %>       		