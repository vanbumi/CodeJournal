## Checking if jquery is loaded using Javascript

	window.onload = function() {
	    if (window.jQuery) {  
	        // jQuery is loaded  
	        alert("Yeah!");
	    } else {
	        // jQuery is not loaded
	        alert("Doesn't Work");
	    }
	}