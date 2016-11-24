# Cut String

Truncate

	<%= truncate(strip_tags(article.body), length: 100) %>

Otherway I forgot yet

	raw and ...	

Othersway

	<%= raw news.konten.truncate(200) %>

*that could be not work in index View

Try also:

	<%= raw post.body.truncate(020) %>		