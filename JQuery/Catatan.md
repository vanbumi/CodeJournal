# Catatan
Selama membuat Rails ramah dengan JQuery Ajax

Di _form.html.erb

	<%= form_for(@koman, remote: true) do |f| %>
  	<% if @koman.errors.any? %>

 asalnya di Rails 5 form_for(koman) do ... 	