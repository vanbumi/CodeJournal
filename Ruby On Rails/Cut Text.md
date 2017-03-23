# Cut String

Truncate

	<%= truncate(strip_tags(article.body), length: 100) %>

Otherway 

	<%= raw product.name[0..40] %>...	


*that could be not work in index View

Try also:

	<%= raw post.body.truncate(020) %>		