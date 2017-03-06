# Form Search

## Form Search Center

	<div class="container">
	    
	  <form id="search-form" class="navbar-form text-center">
	    <div class="form-group">
	      <input type="text" class="form-control" placeholder="Search">
	    </div>
	    <button type="submit" class="btn btn-default">Submit</button>
	  </form>
	  
	</div>

	#search-form {
	  margin-top: 20px;
	  background-color: #666;
	}


## Form Search Responsive

	<form class="searchform">
	  <input type="text" name="s">
	  <input type="submit" value="Search" title="Search Button">
	</form>

	.searchform{
	  position:relative
	}
	.searchform input[type="text"]{
	  background: #EBEBEB;
	  height: auto;
	  -webkit-border-radius: 0;
	  -moz-border-radius: 0;
	  border-radius: 0;
	  margin-bottom: 0;
	  padding: 7px;
	  border: none;
	  float: left;
	  color: #5F5F5F;
	  width: 100%;
	  height: 34px;
	  float: none;
	  padding-right: 70px;
	  -webkit-box-sizing: border-box;
	  -moz-box-sizing: border-box;
	  box-sizing: border-box;
	}
	input[type="submit"]{
	  background: #6B6B6B;
	  border: none;
	  padding: 7px;
	  color: #fff;
	  height: 34px;
	  position: absolute;
	  bottom: 0;
	  right: 0;
	  margin:0
	}
