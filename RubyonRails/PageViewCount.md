# Page Impression

Source:

	https://github.com/charlotte-ruby/impressionist


Manual way:

	http://stackoverflow.com/questions/18601820/creating-a-simple-hit-counter-in-rails

The easiest but very efficient way would be

in the view:

	<% @pages.each do |page| %>
	   <%= page.impressionist_count %> 
	<% end %>	

How to Query

	http://stackoverflow.com/questions/25565621/last-week-most-viewed-items-using-impressionist-gem

	http://stackoverflow.com/questions/27549386/get-impresions-count-from-today-yesterday-and-this-month-impresionist-gem	