### Case dearmom..	

	<% @slider_galeries.each do |slider_galerie| %>
	    <% slider_galerie.img_sliders.each do |image| %>
	            <%= cl_image_tag(image.path, { size: '', crop: :fit }) %>
	        <% end %>            		
	<% end %>