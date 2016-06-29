# Simple Search Form

### products.index.html

	<%= form_tag products_path, :method => 'get' do %>
	    <p>
			<%= text_field_tag :search, params[:search], :placeholder => 'Nama product' %>
		    <%= submit_tag "Search", :name => nil %>
	    </p>
	<% end %>

### ProductsController

	def index
    	@products = Product.search(params[:search]).order("created_at DESC")
  	end

### Product Model

	def self.search(search)
		if search
			where("name LIKE ?", "%#{search}%")
		    # where('location LIKE ?', "%#{search}%")
		else
			all
		end
	end  	