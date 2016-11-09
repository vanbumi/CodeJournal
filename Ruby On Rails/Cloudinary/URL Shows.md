## Do with path (Menampilkan IMAGE URL)

	<%= cl_image_path(gambar.path, :width => 500, :height => 500, :crop => :fill) %>

or

	<%= cl_image_path(gambar.path) %>

or

	<%= cl_image_path(gambar_vaneo.path, :width => 100, :height => 150, :crop => :fill) %>

Put inside form input example 

	<input type="text" class="form-control" value="<%= cl_image_path(gambar_vaneo.path) %>">	

