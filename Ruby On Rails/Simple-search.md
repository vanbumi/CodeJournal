# Simple Search

### View

	<%= form_tag(brands_path, :method => "get", id: "search-form") do %>
		<%= text_field_tag :search, params[:search], placeholder: "Search Brands" %>
		<%= submit_tag "Search" %>
	<% end %>

### Controller

	@brands = Brand.search(params[:search])	

### Model

**Postgresql**

	def self.search(search)
	  where("name ILIKE ?", "%#{search}%") 
	end

**Mysql**

	Product.where('LOWER(name) LIKE LOWER(?)', "%#{params[:search]}%")

	 