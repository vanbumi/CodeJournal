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

Controller:

	@articles = Article.all.order(:created_at => 'DESC').page(params[:page]).per_page(2)

Load the Bootstrap CSS in your template In your view, use the renderer: BootstrapPagination::Rails option with the will_paginate helper:

	<%= will_paginate @...., renderer: BootstrapPagination::Rails %>


### Error

The @news variable appears to be empty. Did you forget to pass the collection object for will_paginate?

Solutions:

Change with this 

	<%= will_paginate @articles, renderer: BootstrapPagination::Rails %>

Base on it controller:

	@articles = Article.all.order(:created_at => 'DESC').page(params[:page]).per_page(2)		