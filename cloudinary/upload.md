# Rails direct Upload to Cloudinary.com

	gem "cloudinary"

bundle install

test in rails console

	$ rails c 

	Cloudinary::Uploader.upload('/home/dyo/Pictures/myphoto.png')

	result =>

Add gem

	gem 'attachinary'

bundle install

application.rb add below:

	require "attachinary/orm/active_record" # active_record atau mongoid

Run rake attachinary:install:migrations

rake db:migrate

Mount attachinary on routes.rb

	mount Attachinary::Engine => "/attachinary"

Generate files javascript as needs :

	rake attachinary:fetch_fileupload # download required js file

Include pada application.js :

	//= require jquery.ui.widget
	//= require jquery.iframe-transport
	//= require jquery.fileupload
	//= require cloudinary/jquery.cloudinary
	//= require attachinary

At last add on header application layout <%= cloudinary_js_config %>

	sample:
	<head>
	  <title>App Keren</title>
	  <%= stylesheet_link_tag    'application', media: 'all' %>
	  <%= javascript_include_tag 'application' %>
	  <%= cloudinary_js_config %>
	  <%= csrf_meta_tags %>
	</head>	

Setup Model:

	validates :images, presence: true
	has_attachments :images, maximum: 5, accept: [:jpg, :png, :gif]


Setup View dan Controller, form Product:

	<%= f.attachinary_file_field :images %>

Finally on controller, add strong parameters. Sample :

	params.require(:product).permit(:name, :price, :description, images: [])

On show.html.erb add bellow :

	<% @product.images.each do |image| %>
    	<%= cl_image_tag(image.path, { size: '125x125', crop: :fit }) %>
	<% end %>	

On index.html.erb use this:

	<% @products.each do |p| %>
		<% product.images.each do |image| %>
	    	<%= cl_image_tag(image.path, { size: '125x125', crop: :fit }) %>
		<% end %>		
	<% end %>

















