# Rails Upload to Cloudinary

## Setup

### Credentials

> Download file cloudinary.yml from the accounts and put that file on folder config/ directory same level as database.yml

##### Add Gemfile

	gem "cloudinary"

##### Bundle

	$ bundle install

##### Test in rails console

	$ rails c 

	Cloudinary::Uploader.upload('/home/dyo/Pictures/myphoto.png')

	result =>

##### Add Gemfile Attachinary

	gem 'attachinary'

##### Bundle	

	$ bundle install

##### Setup file of application.rb add below:

	require "attachinary/orm/active_record" # active_record or mongoid

##### Go to Terminal	

	$ Run rake attachinary:install:migrations

	$ rake db:migrate

##### Mount attachinary on file routes.rb, add this line:

	mount Attachinary::Engine => "/attachinary"

##### Generate files javascript as needs :

	$ rake attachinary:fetch_fileupload # download required js file

##### Include pada application.js :

	//= require jquery.ui.widget
	//= require jquery.iframe-transport
	//= require jquery.fileupload
	//= require cloudinary/jquery.cloudinary
	//= require attachinary

##### At last add on header application layout <%= cloudinary_js_config %>

	<!-- sample: -->
	<head>
	  <title>App Keren</title>
	  <%= stylesheet_link_tag    'application', media: 'all' %>
	  <%= javascript_include_tag 'application' %>
	  <%= cloudinary_js_config %>
	  <%= csrf_meta_tags %>
	</head>	

##### Setup Model:

	validates :images, presence: true
	has_attachments :images, maximum: 5, accept: [:jpg, :png, :gif]


##### Setup View dan Controller, form Product:

	<%= f.attachinary_file_field :images %>

##### Finally on Controller, add strong parameters. Sample :

	params.require(:product).permit(:name, :price, :description, images: [])

##### On file show.html.erb add bellow :

	<% @product.images.each do |image| %>
    	<%= cl_image_tag(image.path, { size: '125x125', crop: :fit }) %>
	<% end %>	

##### On file index.html.erb use this to apply images as loop

	<% @products.each do |product| %>
		<% product.images.each do |image| %>
	    	<%= cl_image_tag(image.path, { size: '125x125', crop: :fit }) %>
		<% end %>		
	<% end %>

















