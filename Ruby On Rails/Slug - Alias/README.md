# Slug or Alias (SEO Friendly)

Create slug column

	rails g migration add_slug_to_posts slug:string

In single Controller

	slug   = params[:slug]
  	@posts = Post.where("slug = ?", slug).limit(1)

or use this

	slug = params[:slug]
    @articles = Article.where("slug = ?", slug).limit(1)

In routes.rb

	# slug bermain disini
	get 'single_post/index'     # >> original

	get ':slug' => 'single_post#index'

or use this

Replace this:	

	get 'single_article/index'

With this:

	get ':slug' => 'single_article#index'	  	

Link

	<a href="/article/<%= post.slug %>"><h3><%= post.name %></h3></a>

Replace with this :

	<a href="/<%= news.slug %>"><h4><%= news.title %></h4></a>

On rails form

	<div>
		<%= f.label :slug %><br>
		<%= f.text_field :slug, id:"slug_name", class: "form-control", placeholder:"slug" %>
	</div>	


Slug script

	<script>
	  $("#name").keyup(function() {
	    var name_val = $("#name").val()
	    // get change
	    var name_s = name_val.replace(/\W+/g, "-");
	    // get small cap
	    var name_small = name_s.toLowerCase();
	    // get copy
	    $("#slug_name").val(name_small)
	  });
	</script>