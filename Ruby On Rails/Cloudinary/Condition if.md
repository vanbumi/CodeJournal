## If image Present?

  <% if @user.photos.present? %>
    <% @user.photos.each do |photo| %>
    <div class="field">
        <%= cl_image_tag(photo.path,
             :width => 200, :height => 200,
             :crop => :thumb, :gravity => :face, :radius => 20
              ) %>
        <br><br>
        <div class="field">
          <strong>URL: </strong><input class="" type="text" value="<%= cl_image_path(photo.path) %>" >
        </div>
    </div>
    <% end %>
  <% else %>
    <div class="field">
        <%= image_tag("user.jpg", size: "200x200", alt: "default-user") %>
    </div>
  <% end %>

## Other example

  <% @users.each do |user| %>
    <tr>
      <td>
        <% if user.photos.present? %>
          <% user.photos.each do |photo| %>
              <%= cl_image_tag(photo.path, { size: '30x30', crop: :fit }) %>
          <% end %>
        <% else %>
          <%= image_tag("user.jpg", size: "30x30", alt: "default-photo") %>
        <% end %>
      </td>

   .....  

## Current_user (index view)

    <% if current_user.photos.present? %>
        <% @users.each do |current_user| %>
            <% current_user.photos.each do |photo| %>
                <%= cl_image_tag(photo.path, { size: '30x30', crop: :thumb }) %>
            <% end %>
         <% end %>
    <% else %>
        <%= image_tag("user.jpg", size: "30x30", alt: "default-photo") %>
    <% end %>


