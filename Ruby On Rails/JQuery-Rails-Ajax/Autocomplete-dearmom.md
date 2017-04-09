# Study case rails autocomplete for dearmom..

Controller :

	Home Controller

Method	

	sortir

View at:

	application.html.erb

form at application.html.erb : 

	<%= form_tag sortir_path do %>
        <%= text_field_tag :sortir, '', size:25  %>
        <%= submit_tag 'Sortir', :id => 'sortir_key' %>
    <% end %>

Change value 'post' to 'get'    

    <form action="/sortir" accept-charset="UTF-8" method="post">
    	<input name="utf8" type="hidden" value="✓">
    	<input type="hidden" name="authenticity_token" value="OQmQqCc+4gdniH0gNj31r9UozsNPuIqsgVgQm557jcXqgx93up+YOrzMWi01NHJRu//2cO7cxthZMzI1yqT0SQ==">
        <input type="text" name="sortir" id="sortir" value="" size="25">
        <input type="submit" name="commit" value="Sortir" id="sortir_key" data-disable-with="Sortir">
	</form>		

become"

	<%= form_tag sortir_path, method: 'get' do %>
        <%= text_field_tag :sortir, '', size:25, :autocomplete => 'off'  %>
        <%= submit_tag 'Sortir', :id => 'sortir_key' %>
    <% end %>

:autocomplete => 'off'

remote: true

Create new file sortir.js.erb

Test with 

	alert("Hello from sortir")

Copy source link from jquery website

	<!--autocomplete-->
	<link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
	<script src="https://code.jquery.com/jquery-1.12.4.js"></script>
	<script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>

Copy code from jquery paste to sortir.js.erb

	$( function() {
	    var availableTags = [
	      "ActionScript",
	      "AppleScript",
	      "Asp",
	      "BASIC",
	      "C",
	      "C++",
	      "Clojure",
	      "COBOL",
	      "ColdFusion",
	      "Erlang",
	      "Fortran",
	      "Groovy",
	      "Haskell",
	      "Java",
	      "JavaScript",
	      "Lisp",
	      "Perl",
	      "PHP",
	      "Python",
	      "Ruby",
	      "Scala",
	      "Scheme"
	    ];
	    $( "#tags" ).autocomplete({
	      source: availableTags
	    });
	  } );

Change $( "#tags" ) become:

	$( "#sortir" )

where sortir id from? show up when inspect element

	<input type="text" name="sortir" id="sortir" value="" size="25" autocomplete="off">

Change the code become like this:

	$( function() {
	    var availableTags = [ "Brandon", "Dyo", "Norma", "Ersya" ];
	    $( "#sortir" ).autocomplete({
	        source: availableTags
	    });
	} );

And change as bellow:

	$( function() {
	    var availableTags = <%= raw @sortir %>;
	    $( "#sortir" ).autocomplete({
	        source: availableTags
	    });
	} );

And update method sortir in home controller

	sortir
		@sortir = [ "Brandon", "Dyo","Norma", "Ersya" ]
	end	

And change:

    sortir
		sor = "%" + params[:sortir] + "%"
    	@sortir = Brand.where('name LIKE ?', sor).pluck('name')
	end

Update assets > application.js

	$(function(){
	    $('#sortir').on('keyup', function(){
	        $('#sortir_key').click();
	    });
	});

Optionally you can use below to remove blank space

	$(function(){
	    $('#sortir').on('keyup', function(){
	        var x = ( $('#sortir').val() ).trim();
	        if (x.length > 0){
	            $('#sortir_key').click();
	        }
	    });
	});

## Video 4

[Autocomplete select](http://api.jqueryui.com/autocomplete/#event-select)

Add new function on application.js

	$(function(){
		$('#sortir').autocomplete({
			select: function(event, ui){
				alert(ui.item.value);
		};
		});
	});

## Video 5

Add into application.html.erb

	<div id="brand_data"></div>

Add into sortir.js.erb

	$('#brand_data').html("<%= j render 'datas' %>")

Create partial file _datas.html.erb

Update home controller 

	def sortir
		@sors = Brand.where("name = ?", params[:sortir])
    	puts @sors.inspect
	end		

For select menu section : The last problem is how to query select_tag	 (solve)

Update application.js

	$(function(){
		$('#sortir').autocomplete({
			select: function(event, ui){
	            setTimeout(function(){
	                $('#sortir_key').click;   
			    	alert(ui.item.value);        
	            },50);
		}
		});
	});

update file _datas.html.erb

	<p><%=  %></p>