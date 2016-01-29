
# Will paginate

## Steps: 

	gem 'will_paginate', '~> 3.1'

bundle install

	@properties = Property.search(params[:search]).order("created_at DESC").page(params[:page]).per_page(5)

To View:
	
	<%= will_paginate @posts, :style => 'color:blue' %>