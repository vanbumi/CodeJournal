# Passing	Variables	to	a	Partial

**example/_footer.html.erb**

	<hr>
	<p>
	Copyright	<%=	start_year	%>	-	<%=	Date.today.year	%>	the	Easter	Bunny.
	</p>

app/views/example/test.html.erb

	<%=	render	partial: "footer", locals: {start_year:	'2000'}	%>

partial, but without the local variable

	<hr>
	<p>
		Copyright
		<%=	"#{start_year}	-	"	if	defined?	start_year	%>
		<%=	Date.today.year	%>
		the	Easter	Bunny.
	</p>