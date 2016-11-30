# Ransack

[Github Ransack](https://github.com/activerecord-hackery/ransack)
[Ransack basic-searching](https://github.com/activerecord-hackery/ransack/wiki/basic-searching)

## Error

	param is missing or the value is empty: product

Solution:

use this as basic form:

	<%= search_form_for @q, url: admin_products_path do |f| %>
		...
	<% end %>	

My complete form and not using label:

	<%= search_form_for @q, url: admin_products_path, class:'form-inline pull-right', :method => 'get' do |f| %>
		<div class="form-group">
		  <% f.label :name_cont %>
		  <%= f.search_field :name_cont, class:'form-control' %>
		</div>
		  <%= f.submit class:'btn btn-default' %>
	<% end %>

Index Controller:
	
	def index
		@q = Product.ransack(params[:q])
	    @products = @q.result.order("created_at DESC").page(params[:page]).per_page(10)
    end		

## Ransack's sort_link

	<table class="table table-hover">
		<thead>
			<tr>
			  <th><span class="glyphicon glyphicon-ok"></span></th>
			  <th><%= sort_link(@q, :name, 'Nama') %></th>
			  <th><%= sort_link(@q, :size, 'Ukuran') %></th>
			  <th><%= sort_link(@q, :thickness, 'Ketebalan') %></th>
			  <th><%= sort_link(@q, :category, 'Kategori') %></th>
			  <th><%= sort_link(@q, :publish, 'Publish') %></th>
			  <th colspan="3" class="text-center">Actions</th>
			</tr>
		</thead>
		<tbody>

		...    