# jQuery	

	$('img').hover(makeBigger, returnToOriginalSize);

	    function makeBigger() {
	        $(this).css({height: '+=50%', width: '+=50%'});
	    }
	    function returnToOriginalSize() {
	        $(this).css({height: "", width: ""});
	    }
