# Each slice do and Each with index do

	<section id="portfolio" class="container main">
	  <% @categories.each_slice(4) do |category| %>
	    <div class="row">
	    <% category.each_with_index do |categ, index| %>
	      <ul class="gallery col-4">
	        <% categ.gambars.each do |gambar| %>
	          <!--Item 1-->
	          <li>
	            <div class="preview">
	              <%= cl_image_tag gambar.path, { size: '270x270', crop: :thumb } %>

**Do not forget to give row after slice**

Jadi each_slice itu looping row nya.

**Steps**: 

1. each_slice().
2. class row.
3. each do normal seperti biasa.
4. each do for image.

Example case : grafika

	<section id="portfolio" class="container main">
	  <% @categories.each_slice(4) do |category| %>
	    <div class="row">
	    <% category.each_with_index do |categ, index| %>
	      <ul class="gallery col-4">
	        <% categ.gambars.each do |gambar| %>
	          <!--Item 1-->
	          <li>
	            <div class="preview">
	              <%= cl_image_tag gambar.path, { size: '270x270', crop: :thumb } %>
	              <div class="overlay">
	              </div>
	              <div class="links">
	                <a data-toggle="modal" href="#modal-<%= index %>"><i class="icon-eye-open"></i></a><a href="/products/<%= categ.id %>"><i class="icon-link"></i></a>
	              </div>
	            </div>
	            <div class="desc">
	              <h5>:: <%= index %> | <%= categ.name %></h5>
	              <small><%= truncate(strip_tags(categ.keterangan), length: 50) %>...</small>
	            </div>
	            <div id="modal-<%= index %>" class="modal hide fade">
	              <a class="close-modal" href="javascript:;" data-dismiss="modal" aria-hidden="true"><i class="icon-remove"></i></a>
	              <div class="modal-body">
	                <%= cl_image_tag(gambar.path, :width => 470, :height => 380, :crop => :fill, :gravity => false) %>
	              </div>
	            </div>
	          </li>
	          <!--/Item 1-->
	        <% end %>
	      </ul>
	    <% end %>
	    </div>
	  <% end %>
	</section>

**Simple case grafika at show page**

	<% @products1.each_slice(4) do |product| %>
		<div class="img-spasi text-center"> # --->> berlaku sebagai ROW !
		<% product.each do |photo| %>
			<div class="span3 img">
				<% photo.photos.each do |foto| %>
				<a class="example-image-link" href="<%= cl_image_path(foto.path, :width => 900, :height => 700, :crop => :thumb) %>" data-lightbox="example-1" data-title="<%= photo.noproduct %> | <%= photo.name %>">
						<%= cl_image_tag foto.path, { size: '150x150', crop: :thumb } %>
					<% end %>
				</a>	
				<h5><%= photo.noproduct %> - <%= photo.name %></h5>
			</div>
			<% end %>
		</div>
	<% end %>	
	
### Readmore this 

[ruby-array-each-slice-with-index](http://stackoverflow.com/questions/5983977/ruby-array-each-slice-with-index)	

