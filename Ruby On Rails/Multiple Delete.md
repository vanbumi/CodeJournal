# Rails multiple delete checkbox

[rails-3-delete-multiple-records-using-checkboxes](http://stackoverflow.com/questions/12711178/rails-3-delete-multiple-records-using-checkboxes)

## Steps

Create checkbox:

	<%= check_box_tag 'product_ids[]', product.id %>

Create submit button:

	<%= submit_tag 'Multi Delete' %>

Create Heading for checkbox	

	<th></th>

Wrapp with form tag

	<%= form_tag multi_delete_admin_products_path, method: :delete do %>

	...

	<% end %>

Update config > routess.rb

	namespace :admin do
	    resources :products do
	      collection do
	        delete :multi_delete
	      end
	    end
	end

Update products_controller

	def multi_delete
	    Product.destroy(params[:product_ids])
	    redirect_to admin_products_path
	end

Example:

	<%= form_tag multi_delete_admin_products_path, method: :delete do %>
	<table class="table table-hover">
	  <thead>
	  <tr>
	    <th></th>
	    <th>Nama</th>
	    <th>Ukuran</th>
	    <th>Publish</th>
	    <th>Actions</th>
	  </tr>
	  </thead>
	  <tbody>
	  <% @products.each do |product| %>
	  <tr>
	    <td>
	      <%= check_box_tag 'product_ids[]', product.id %>
	    </td>
	    <td><%= product.name %></td>
	    <td><%= product.size %></td>
	    <td><%= product.publish %></td>
	    <!--<td>...</td>-->
	    <td>
	      <% link_to 'show', admin_product_path(product), class:'btn btn-primary btn-xs' %>
	      <%= link_to 'edit', edit_admin_product_path(product), class:'btn btn-success btn-xs' %>
	      <%= link_to 'delete', admin_product_path(product), class:'btn btn-danger btn-xs', method: :delete, data: {confirm: 'Are your sure'}  %>
	    </td>
	  </tr>
	  <% end %>
	  </tbody>
	</table>
	<%= submit_tag 'Multi Delete' %>
	<% end %>

Example:

![example-image](http://res.cloudinary.com/medio/image/upload/v1477453390/multy_delete_g7lqc8.png)		