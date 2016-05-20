# Slug or Alias (SEO Friendly)

In single Controller

	slug   = params[:slug]
  	@posts = Post.where("slug = ?", slug).limit(1)

In routes.rb

	# slug bermain disini
	get 'single_post/index'     # >> original

	get ':slug' => 'single_post#index'  	

In view

	<a href="/article/<%= post.slug %>"><h3><%= post.name %></h3></a>


