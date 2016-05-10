# Learning Spot jQuery

## Menu

[Like Star Love Etc](https://github.com/vanbumi/CodeJournal/blob/master/jQuery/Like-Star-Love-Etc.md) 
[Image Bigger](https://github.com/vanbumi/CodeJournal/blob/master/jQuery/img-bigger.md)

[Examples](http://www.w3schools.com/jquery/jquery_examples.asp)

[Do you want to develop your jQuery selector skills?](http://www.w3schools.com/jquery/trysel.asp)

[Working_with_javascript_in_rails](http://edgeguides.rubyonrails.org/working_with_javascript_in_rails.html)

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

## On Change

* [jQuery change event > this super video](https://www.youtube.com/watch?v=B1mU0Uk_Qs4)
* [Super Videos](https://www.youtube.com/watch?v=a59kOE2Ma1Q&list=PL6n9fhu94yhVDV697uvHpavA3K_eWGQap)
