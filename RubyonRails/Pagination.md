
# Will paginate

## Steps: 

	gem 'will_paginate', '~> 3.1'

bundle install

	@properties = Property.search(params[:search]).order("created_at DESC").page(params[:page]).per_page(5)

To View:
	
	<%= will_paginate @posts, :style => 'color:blue' %>

## Will_Paginate Bootstrap

* [will_paginate-bootstrap](https://rubygems.org/gems/will_paginate-bootstrap/versions/1.0.1)
* [Github](https://github.com/bootstrap-ruby/will_paginate-bootstrap)

