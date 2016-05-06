# Rails Upload to Cloudinary

## Setup

### Credentials

> Download file cloudinary.yml from the accounts and put that file on folder config/ directory same level as database.yml

##### Add Gemfile

	gem "cloudinary"
	gem "cloudinary"

##### Bundle

	$ bundle install

##### Test in rails console

	$ rails c 

	Cloudinary::Uploader.upload('/home/dyo/Pictures/manwalk.png')

	result => {"public_id"=>"xqpzzuqpwa3azw2z43rm", "version"=>1461598407, "signature"=>"5b5ca34daa149934c43daefd9f6fd77d5537ed79", "width"=>175, "height"=>372, "format"=>"png", "resource_type"=>"image", "created_at"=>"2016-04-25T15:33:27Z", "tags"=>[], "bytes"=>56448, "type"=>"upload", "etag"=>"d8c3478e3ceec838ae3801fe374852ee", "url"=>"http://res.cloudinary.com/cmp-batam/image/upload/v1461598407/xqpzzuqpwa3azw2z43rm.png", "secure_url"=>"https://res.cloudinary.com/cmp-batam/image/upload/v1461598407/xqpzzuqpwa3azw2z43rm.png", "original_filename"=>"manwalk"}

	**Upload is success

Error 1:	Errno::ENOENT: No such file or directory @ rb_sysopen

	Solution:	Directory path incorrect > fix the path	

Error 2:    CloudinaryException: Must supply api_key

	Solution: gem "cloudinary" should be double quotes

	**This case is on sorongbis website


##### Add Gemfile Attachinary

	gem 'attachinary'

##### Bundle	

	$ bundle install

##### Setup file of application.rb add this line below:

	require "attachinary/orm/active_record" # active_record or mongoid

##### Go to Terminal	

	$ rake attachinary:install:migrations

	$ rake db:migrate

##### Mount attachinary on file routes.rb, add this line:

	mount Attachinary::Engine => "/attachinary"

##### Generate files javascript as needs :

	$ rake attachinary:fetch_fileupload # download required js file

##### Include on application.js (on cmpbatam its not necessary when do rake above)

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

##### Error Failed to upload

	Solutions: images: [] ----> on controller strong parameter 	

## Ask Question?

[Ask Question](https://www.bountysource.com/teams/attachinary/issues?tracker_ids=286322)















