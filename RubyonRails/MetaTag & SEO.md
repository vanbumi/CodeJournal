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