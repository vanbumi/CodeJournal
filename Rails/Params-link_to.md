# How to put params on url helper

URL:

	<%= link_to brand.name, product_brand_path(:brand => brand.id) %>

Controller:

	@probrands = Product.where("brand_id = ?", params[:brand])

Will show in Browser:

	http://localhost:3000/product-brand?brand=2

Will show in Inspect element:

	<a href="/product-brand?brand=2">Baby Einstein</a>

---

### Params for filter

Controller :

	@brands = Brand.where(:category_id => params[:id] )

Url :

	<% @brands.each do |brand| %>
		<%= link_to brand.name, product_brand_path(:brand => brand.id) %> <br>
	<% end %>
