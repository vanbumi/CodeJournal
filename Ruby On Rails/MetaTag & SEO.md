# Rails Meta Tag & Seo

Google

	https://www.google.co.id/search?q=how+to+create+meta+tag+rails&oq=how+to+create+meta+tag+rails&aqs=chrome..69i57.8708j0j7&sourceid=chrome&es_sm=122&ie=UTF-8

Meta Tags

	https://github.com/kpumuk/meta-tags

Meta Tags Usage

	https://github.com/kpumuk/meta-tags#metatags-usage

Others	 

	https://github.com/lassebunk/metamagic

	http://cookieshq.co.uk/posts/easy-seo-metatags-with-rails-4/

	http://davidlesches.com/blog/elegant-titles-and-seo-meta-tags-in-rails


### Using content_for

On index.html.erb write this: 

	<%= content_for :meta_tags do %>

		<meta name="twitter:card" content="summary" />
		<meta name="twitter:title" content="<%= @dynamic_title %>" />
		<meta name="twitter:description" content="<%= @dynamic_descr %>" />
		<meta name="twitter:image" content="" />
		<meta name="twitter:domain" content="<%= @dynamic_domain %>" />

	<% end %>
⁠
And on apllication layout inside head tag: 

	<head>

		<%= yield :meta_tags %>

	</head>	

### Meta Core

	<!-- start meta -->
  	<meta charset="utf-8">
  	<meta http-equiv="X-UA-Compatible" content="IE=edge">
  	<meta name="viewport" content="width=device-width, initial-scale=1">
	
  	<!-- global -->
  	<meta name="Author" content="<%= @dynamic_author %>" />

  	<!-- google -->
  	<meta name="description" content="<%= @dynamic_descr %>" />
  	<meta name="keywords" content="<%= @dynamic_keywords %>" />

	<!-- facebook -->
  	<meta property="og:title" content="<%= @dynamic_title %>" />
  	<meta property="og:type" content="article" />
  	<meta property="og:site_name" content="<%= @dynamic_title %>" />
  	<meta property="og:image" content="" />
  	<meta property="og:description" content="<%= @dynamic_descr %>" />
  
  	<meta property="fb:app_id" content="" />
  
  	<!-- twitter -->
  	<meta name="twitter:card" content="summary" />
  	<meta name="twitter:title" content="<%= @dynamic_title %>" />
  	<meta name="twitter:description" content="<%= @dynamic_descr %>" />
  	<meta name="twitter:image" content="" />
  	<meta name="twitter:domain" content="<%= @dynamic_domain %>" />
	<!-- end meta -->	