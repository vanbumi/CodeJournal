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

> Do not forget to giv row after slice

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
	