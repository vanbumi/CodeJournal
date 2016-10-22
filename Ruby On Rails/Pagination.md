# Will paginate

* [Github](https://github.com/bootstrap-ruby/will_paginate-bootstrap)

## Steps: 

	gem 'will_paginate', '~> 3.1'

bundle install

	@properties = Property.search(params[:search]).order("created_at DESC").page(params[:page]).per_page(5)

To View:
	
	<%= will_paginate @posts, :style => 'color:blue' %>

## Will_Paginate Bootstrap

* [will_paginate-bootstrap](https://rubygems.org/gems/will_paginate-bootstrap/versions/1.0.1)

### Install

	gem install will_paginate-bootstrap, or

For projects using Bundler, add gem 

	'will_paginate-bootstrap' to your Gemfile (and then run bundle install).

### Usage

Load the Bootstrap CSS in your template In your view, use the renderer: BootstrapPagination::Rails option with the will_paginate helper:

	<%= will_paginate @collection, renderer: BootstrapPagination::Rails %>