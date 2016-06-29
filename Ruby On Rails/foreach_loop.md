# Ruby on rails foreach with bootstrap3 row class

![gambar loop](http://res.cloudinary.com/medio/image/upload/v1459852106/foreachloop_i5ivcm.png)

## Use Enumerable each_slice

	<% @properties.each_slice(3) do |properties| %>

        <div class="row">
          <% properties.each do |property| %>
              <% property.images.each do |image| %>

            <div class="col-md-4 artikel">
              <div class="thumbnail">
                <%= cl_image_tag(image.path, { size: '300x250', crop: :fit }) %>
                <div class="caption text-left">
                  <h3><%= property.name %> |
                    <% if property.status == "For Sale" %>
                        <span class="label label-danger" role="label"><%= property.status %></span></h3>
                    <% elsif property.status == "Dijual" %>
                        <span class="label label-danger" role="label"><%= property.status %></span></h3>
                    <% else %>
                        <span class="label label-warning" role="label"><%= property.status %></span></h3>
                    <% end %>
                  <p class="pull-right"><span class="label label-primary"><strong><%= number_to_currency(property.price, precision:0, unit:"Rp.", delimiter: ".") %></strong></span></p>
                  <ul class="list-unstyled">
                    <li><i class="fa fa-university"></i>&nbsp;<%= property.property_type %></li>
                    <li><i class="fa fa-expand"></i>&nbsp;&nbsp;<%= property.area %></li>
                    <li><i class="fa fa-bed"></i>&nbsp;<%= property.bedroom %>&nbsp;Bedroom</li>
                    <li><i class="fa fa-tint"></i>&nbsp;&nbsp;&nbsp;<%= property.bathroom %>&nbsp;Bathroom</li>
                  </ul>
                  <p><a href="/<%= property.slug %>" class="btn btn-primary" role="button" style="color:#FFFFFF;">Lihat Detail</a></p>
                </div>
              </div>
            </div>
            
            <% end %>
          <% end %>
        </div>
    <% end %>