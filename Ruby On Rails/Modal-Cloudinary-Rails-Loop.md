# How Modal can Work in Rails Loop with Cloudinary Images

[Stack Overflow](http://stackoverflow.com/questions/40490801/css-not-working-right-when-using-do-loop-in-bootstrap-modal-in-rails-app)

Step 1: Create loop with index

	<% @categories.each_with_index do |product, index| %>
		...
		...
	<% end %>	 

Step 2: View image

	<% product.gambars.each do |gambar| %>
    	<%= cl_image_tag(gambar.path, {
	        :width => 270, :height => 180, :crop => :thumb,
	        :gravity => false }) %>
		...
		...
	<% end %>	

Step 3: Create link Modal for each image

	<div class="links">
	  <a data-toggle="modal" href="#modal-<%= index %>"><i class="icon-eye-open"></i></a><a href="#"><i class="icon-link"></i></a>
	</div>

Step 4: Create Modal

	<div id="modal-<%= index %>" class="modal hide fade">
	    <a class="close-modal" href="javascript:;" data-dismiss="modal" aria-hidden="true"><i class="icon-remove"></i></a>
	    <div class="modal-body">
	      <%= cl_image_tag(gambar.path, {
	          :width => 570, :height => 400, :crop => :thumb,
	          :gravity => false }) %>
	      <!-- <img src="/themefront/images/portfolio/full/item1.jpg" alt=" " width="100%" style="max-height:400px"> -->
	    </div>
	</div>
	<% end %>	

