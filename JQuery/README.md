# Learning Spot jQuery

## Menu

[Like Star Love Etc](https://github.com/vanbumi/CodeJournal/blob/master/jQuery/Like-Star-Love-Etc.md) 
[Image Bigger](https://github.com/vanbumi/CodeJournal/blob/master/jQuery/img-bigger.md)

[Examples](http://www.w3schools.com/jquery/jquery_examples.asp)

## On Key Up

### Name Alias (slug)

On Rails form helper

	<%= f.text_field :name, class:"form-control", id:"name"  %>
	<%= f.text_field :slug, id:"name_slug", class:"form-control" %>	

	$("#name").keyup(function() {
	    var name_val = $("#name").val()
	    var name_s = name_val.replace(/\W+/g, "-");
	    var slug = name_s.toLowerCase();

	    $('#name_slug').val(slug);
	});


