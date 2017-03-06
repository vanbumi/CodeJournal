# Simple Rails Web-Shop 

### Steps 1

Create app

	rails new web-shop -d postgresql

Setup database	

Create Home Page

	rails g controller home index

update root

	home#index	


Create About Page

	rails g controller about index

Cek browser

	rails server	

About Controller

	def index
		@page_title = 'About Us'
	end 

View index

	<h1><%= @page_title %></h1>

Create product scaffold

	rails g scaffold product name category_id:integer subcategory_id:integer brand_id:integer weight:decimal dimention discount:decimal price_awal:decimal price_sekarang:decimal status description:text

Create category scaffold

	rails g scaffold category name

Create subcategory scaffold

	rails g scaffold subcategory name

Create brand scaffold

	rails g scaffold brand name

Edit layout > application.html.erb

Add bootstrap cdn

* Get 3 meta from the top, paste below title

* Copy navbar and paste below body

* Copy the css :

		body {
			padding-top: 50px;
		}


* Get ride of Branding on navbar

* Change to navbar-default

* Change the link to be link_to "Home", root_path	

* Get the dropdown link from the bootsrap component

### Steps 2

**Create header**

		<header>
			<div class="container">
				<h1>Dear Mom <small><%= @page_title ? @page_title : 'Welcome'  %></small></h1>
			</div>
		</header>

Copy and paste on title

	<%= @page_title ? @page_title : 'Welcome'  %>

Create condition for active page

	<li class="<%= params[:controller] == 'home' ? 'active' : '' %>"><%= link_to 'Home', root_path %></li>
	<li class="<%= params[:controller] == 'about'  ? 'active' : '' %>"><%= link_to 'About', about_index_path %></li>
	<li class="<%= params[:controller] == 'contact'  ? 'active' : '' %>"><%= link_to 'Contact', contact_index_path %></li>

Create tag section outside yield

	<section>
		<div class="container">
			<div class="row">
				<div class="col-md-4">
					<%= render 'partials/sidebar' %>
				</div>
				<div class="col-md-8">
					<%= yield %>
				</div>	
			</div>
		</div>
	</section>

In view folder Create partials folder and file _sidebar.html.erb

	test with sidebar word

Create footer:

	<footer>
		<div class="container">
			<p>Copyright &copy; 2017 Dear Mom Baby Shop, All Right Reserved</p>
		</div>
	</footer>

Create style css in application.css

	body {
		font-family: 'Arial', sans-serif;
		font-size: 14px;
		color:#666;
		line-height:1.5px; 
	}

	header {
		background:#333;
		color:#fff;
		height:80px;
		margin-bottom:20px;
	}

	footer {
		background:#333;
		color:#fff;
		height:60px;
		text-align:center;
		margin-top:20px;
		padding-top:20px; 
	}	

Move address on about into sidebar:

	.............
	.............

And give condition only show on about:

<% if params[:controller] == 'about' %>
	..................
<% end %>

### Part 3 Create static homepage

In home index

	<div id="home-index">
	    <div class="row">
	        <div class="col-md-4 col-sm-4">
	            <h3>Product 1</h3>
	            <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="">
	            <%= link_to 'Buy', '#' %>	
	        </div>
	        <div class="col-md-4 col-sm-4">
	            <h3>Product 2</h3>
	            <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="">
	        </div>
	        <div class="col-md-4 col-sm-4">
	            <h3>Product 3</h3>
	            <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="">
	        </div>
	    </div>

	    <div class="row">
	        <div class="col-md-4 col-sm-4">
	            <h3>Product 4</h3>
	            <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="">
	        </div>
	        <div class="col-md-4 col-sm-4">
	            <h3>Product 5</h3>
	            <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="">
	        </div>
	        <div class="col-md-4 col-sm-4">
	            <h3>Product 6</h3>
	            <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="">
	        </div>
	    </div>
	</div>

Get 6 product and image from klik baby, upload to cloudinary.

	Create css:

		#home-index {
			text-align: center;
		}

		#home-index img {
		  width: 100%;
		  padding: 3px;
		  border: 1px #ccc solid;
		}

		#home-index .btn {
			display: block;
			margin-top:20px;
		}

		#home-index h3 {
			height: 50px;
		}
	
Get list group from getbootstrap.com

	<div class="list-group">
	  <a href="#" class="list-group-item active">
	    Cras justo odio
	  </a>
	  <a href="#" class="list-group-item">Dapibus ac facilisis in</a>
	  <a href="#" class="list-group-item">Morbi leo risus</a>
	  <a href="#" class="list-group-item">Porta ac consectetur ac</a>
	  <a href="#" class="list-group-item">Vestibulum at eros</a>
	</div>

### Part 4

Create new layout for admin pages

Create new file admin_layout.html.erb

Remove column

In product controller add layout 'admin_layout'

Edit products index

Add image_url field

	rails g migration add_image_url_to_products image_url:string

Add image_url at controller product_params		

Add form image_url to form 

Edit product show

Add image link

Remove sidebar (change layout render)

In home Controller Create new action show

Create new routes for home > show 
	
	get 'show/:id' => 'home#show' 

Create new file show.html.erb in home folder

Copy from product show to home show

View at localhost:3000/show/1

Create link from home display to show by :id 

	<% @products.each do |product| %>
	<a class="btn btn-primary" href="/show/<%= product.id %>">Lihat</a>
	<% end %>

Dont forget to update home controller index:

class HomeController < ApplicationController

	def index
		@products = Product.all
	end	

Edit style of home index

	#home-index img {
	  padding: 3px;
	  width: 100%;
	  height: auto;
	}

	#home-index .image {
	  padding-top: 0px;
	  padding-bottom: 20px;
	}

	#home-index .image:hover {
	  box-shadow: 0px 0px 20px #ccc;
	}

Edit home index become ruby loops

	<div class="row">
		<% @products.each do |product| %>
		    <div class="col-md-4 col-sm-4 image">
		        <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="">
		        <h4><%= product.name %></h4>
		        <a class="btn btn-primary" href="/show/<%= product.id %>">Lihat</a>
		    </div>
		<% end %>    
	</div> 

Create status icon

	<div class="status">
	    <span class="label label-default"><%= product.status %></span>
	</div>	

Fix logo

### Part 5 Edit Product index and product form

Fix categories

give layout admin on subcategories controller

Show category on sidebar

Fix subcategories

give layout admin on subcategories controller

fix form

add column category_id on model subcategories

	rails g migration add_category_id_to_subcategories category_id:integer

Create search form helper

This:

	<form class="searchform">
		<div class="form-group text-center">
		  <input type="text" name="s" class="form-control">
		  <input 
		    type="image" 
		    class="search_img"
		    src="http://res.cloudinary.com/dearmombabyshop/image/upload/c_scale,h_60,w_60/v1488600494/search-pointer-icon_cs1jir.png">
		</div>    
	</form>

to become this:	

	<%= form_tag search_path, method:'get', class:'searchform' do  %>
      <div class="form-group text-center">
        <%= text_field_tag :search, '', size:25 %> 
        <%= submit_tag 'Search', 
          :type => :image, 
          :src => "http://res.cloudinary.com/dearmombabyshop/image/upload/c_scale,h_60,w_60/v1488600494/search-pointer-icon_cs1jir.png", 
          :id => 'search_key' %>
      </div>
    <% end %>

Create method search in home controller

	def search
		@categories = Category.all.order(:created_at => 'DESC')
	end




Create file search.html.erb






























