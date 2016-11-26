# Page Impression

### Source:

[impressionist-github](https://github.com/charlotte-ruby/impressionist)

### Logs an impression

**Logs Impression** adalah menghitung berapa kali (me-log) halaman ditampilkan atau dibaca oleh pengunjung. 

* It can log page impressions (technically action impressions)
* You can log impressions multiple times per request.
* And you can also attach it to a model.

> The goal of this is to provide **customizable stats** that are immediately accessible in your application as opposed to using Google Analytics and pulling data using their API.

##### Installation

Add it to your Gemfile

	gem 'impressionist'

Install with Bundler

	bundle install








---


#### Manual way:

[creating-a-simple-hit-counter-in-rails](http://stackoverflow.com/questions/18601820/creating-a-simple-hit-counter-in-rails)

#### The easiest but very efficient way would be

in the view:

	<% @pages.each do |page| %>
	   <%= page.impressionist_count %> 
	<% end %>	

#### How to Query

[most-viewed-items-using-impressionist-gem](http://stackoverflow.com/questions/25565621/last-week-most-viewed-items-using-impressionist-gem)

[get-impresions-count-from-today-yesterday-and-this-month](http://stackoverflow.com/questions/27549386/get-impresions-count-from-today-yesterday-and-this-month-impresionist-gem)	