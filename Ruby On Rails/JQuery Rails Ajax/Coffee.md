# Coffee script

### Page load

	$(document).on "turbolinks:load" ->
	  alert "The page has loaded !!"

### Contoh penggunaan

	$(document).on "turbolinks:load", ->
	  $("#new_link").click ->
	     alert "Horee"
