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


## Good example for index view

Model

    articleimages
    
Basic

    <% @articles.each do |news| %>

    <% if news.articleimages.present? %>
        <% news.articleimages.each do |image| %>
          <p>
            <%= cl_image_tag(image.path, :width => 720, :height => 350,
              :crop => :thumb, :radius => 0) %>
          </p>
        <% end %>
    <% else %>
        <img src="http://placehold.it/720x350" alt="">
    <% end %>    

Case example

    <div class="blog-item well">
        <% @articles.each do |news| %>
          <a href="#"><h2><%= news.title %></h2></a>
          <div class="blog-meta clearfix">
              <p class="pull-left">
                <i class="icon-user"></i> by <a href="#"><%= news.author %></a> | <i class="icon-folder-close"></i> Category <a href="#"><%= news.category %></a> |
                <i class="icon-calendar"></i> <%= news.created_at.strftime("%d %B %Y, %H:%M") %>
              </p>
            <!-- <p class="pull-right"><i class="icon-comment pull"></i> <a href="blog-item.html#comments">3 Comments</a></p> -->
          </div>

          <% if news.articleimages.present? %>
            <% news.articleimages.each do |image| %>
              <p>
                <%= cl_image_tag(image.path, :width => 720, :height => 350,
                  :crop => :thumb, :radius => 0) %>
              </p>
            <% end %>
          <% else %>
                    <img src="http://placehold.it/720x350" alt="">
        <% end %>

        <p>
          <%= truncate(strip_tags(news.konten), length: 400) %>
        </p>
        <a class="btn btn-link" href="/news/<%= news.id %>">Read More <i class="icon-angle-right"></i></a><br><br>

        <% end %>
    </div>

**Baby-shop case in view show**

    <% if @product.images? %>
        <% @product.images.each do |image| %>
            <%= cl_image_tag(image.path, { size: '500x500', crop: :fit }) %>
        <% end %>
    <% else %>
        <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="" class="img-responsive">
    <% end %>

And use this for view index, with no @

    <% if product.images? %>
        <% product.images.each do |image| %>
            <%= cl_image_tag(image.path, { size: '800x800', crop: :fit, class:'img-responsive' }) %>
        <% end %>
    <% else %>
        <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="" class="img-responsive">
    <% end %>
