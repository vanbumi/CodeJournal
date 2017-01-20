# Image Gallery HTML & CSS

### The html

	<section>
	  <div class="container">
	    <div id="gallery">
	      <h2>Ragam Kenangan</h2>
	      <div class="row">
	        <div class="col-md-3">
	          <div class="photo photo-type-line">
	            <a href="http://placehold.it/350x350" class="photo-hover">
	              <div class="photo-info">
	                <div class="headline">Lorem Ipsum</div>
	                <div class="line"></div>
	                <div class="desc">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Fusce rhoncus urna sed pharetra consequat. Nulla viverra mauris est. Curabitur tempus rutrum rhoncus
	                </div>
	              </div>
	              <div class="mask"></div>
	            </a>
	            <div class="photo-img"><img src="http://placehold.it/350x350" alt=""></div>
	          </div>
	        </div>
		...	
	...

### The css

	  body {
	    font-family: 'Georgia', 'Arial', Sans-serif;
	  }
	  .navbar {min-height: 38px; margin-bottom: 28px !important; border-radius: 0; }
	  .navbar .navbar-brand {padding: 0 12px; font-size: 16px; line-height: 38px; height: 38px;}
	  .navbar .navbar-nav > li > a {padding-top: 0px; padding-bottom: 0px; line-height: 38px; color: #ffffff;}
	  .navbar .navbar-toggle {margin-top: 3px; margin-bottom: 0px; padding: 8px 9px;}
	  .navbar .navbar-form {margin-top: 2px; margin-bottom: 0px;}
	  .navbar .navbar-collapse {border-color:#A40303; }

	  h1, h2 {
	    margin-bottom: 30px;
	  }
	  #gallery img {
	    width: 100%;
	  }
	  .col-md-3 {
	    padding: 0;
	  }
	  footer {
	    margin-top: 30px;
	    height: 40px;
	    background: #333;
	    color: #fff;
	    text-align: center;
	    padding-top: 10px;
	  }
	  .photo {
	    text-align: center;
	    position: relative;
	  }
	  .photo,
	  .photo-hover,
	  .photo-hover .mask,
	  .photo-img,
	  .photo-info {
	    width: 300px;
	    height: 200px;
	  }
	  .photo-img,
	  .photo-hover,
	  .photo-hover .mask {
	    position: absolute;
	    top: 0;
	    left: 0;
	  }
	  .photo-type-line .photo-hover {
	    z-index: 100;
	    -webkit-transition: all 300ms ease-out;
	    -moz-transition: all 300ms ease-out;
	    transition: all 300ms ease-out;
	    opacity: 0;
	    cursor: pointer;
	    display: block;
	    text-decoration: none;
	    text-align: center;
	  }
	  .photo-type-line .photo-info {
	    z-index: 10;
	    color: #fff;
	    display: table-cell;
	    vertical-align: middle;
	    position: relative;
	  }
	  .photo-type-line .photo-info .headline {
	    font-size: 20px;
	  }
	  .photo-type-line .photo-info .line {
	    height: 1px;
	    width: 0px;
	    margin: 15px auto;
	    background: #fff;
	    -webkit-transition: all 500ms ease-out;
	    -moz-transition: all 500ms ease-out;
	    transition: all 500ms ease-out;
	  }
	  .photo-type-line .photo-hover .mask {
	    background: #000;
	    filter: alpha(opacity=50);
	    opacity: 0.5;
	    z-index: 0;
	  }
	  .photo-type-line .photo-hover:hover .line {
	    width: 40px;
	  }
	  .photo-type-line .photo-hover:hover {
	    opacity: 1;
	  }
	  .photo-img {
	    background: #7a548f;
	    z-index: 0;
	  }

### Combine with The lightbox

[lightbox2](http://lokeshdhakar.com/projects/lightbox2/)

Which is add this :

	<a href="http://placehold.it/350x350" class="photo-hover" data-lightbox="my-images" data-title="Lorem Ipsum">

	data-lightbox="my-images" data-title="Lorem Ipsum"

### Create category or any dynamic from database

video 5, 10:12	