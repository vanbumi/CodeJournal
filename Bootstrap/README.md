# All About Bootstrap

### Bootsnip

	http://bootsnipp.com/

Toggle navbar with Slide Down Animation	

	http://bootsnipp.com/snippets/featured/toggle-navbar-with-slide-down-animation

Slide Nav Sidebar

	http://bootsnipp.com/snippets/Ba7vQ

SLIDE LEFT

	http://bootsnipp.com/snippets/NBOK0

Mega menu slide

	http://bootsnipp.com/snippets/E7my0

Mega menu slide down on hover with carousel

	http://bootsnipp.com/snippets/gj9W5

Admin Lists Panel

	http://bootsnipp.com/snippets/featured/admin-lists-panel

Panel, Admin, Progressbar

[Click](http://bootsnipp.com/snippets/pen37)

Admin Panel Quick Shortcuts

	http://bootsnipp.com/snippets/featured/admin-panel-quick-shortcuts

Table Dropdown ProgressBar

	http://bootsnipp.com/snippets/mp0Qz

Admin Side Menu

	http://bootsnipp.com/snippets/featured/admin-side-menu

	Use this:

	widyobumi.ga

Admin Nav Bar with Popup Sign in"

	http://bootsnipp.com/snippets/featured/admin-nav-bar-with-popup-sign-in

Side and Top Navbar Responsive

	http://bootsnipp.com/snippets/BaeOB	

* [Slide Nav Sidebar](http://bootsnipp.com/snippets/Ba7vQ)
* [offcanvas](http://www.jasny.net/bootstrap/javascript/#offcanvas) | [Home Page](http://www.jasny.net/bootstrap/)	
* [Side Navigation](http://www.w3schools.com/howto/howto_js_sidenav.asp)
* [Dashboard](http://bootsnipp.com/snippets/featured/flat-responsive-dashboard-design)

## Will_paginate-bootsrap

[will_paginate-bootstrap](https://github.com/bootstrap-ruby/will_paginate-bootstrap)	

## Nice Sign Up & Login Form for Rails

### Sign Up

	<div class="container">
	  <div class="row main">
	    <div class="panel-heading">
	      <div class="panel-title text-center">
	        <h1 class="title">Sign Up</h1>
	        <hr />
	      </div>
	    </div>

	    <div class="main-login main-center">

	      <%= form_for(resource, as: resource_name, class: 'form-horizontal', url: registration_path(resource_name)) do |f| %>
	        <%= devise_error_messages! %>

	        <div class="form-group">
	          <%= f.label :email, 'Your Email', class:'cols-sm-2 control-label' %><br />
	          <div class="cols-sm-10">
	            <div class="input-group">
	              <span class="input-group-addon"><i class="fa fa-envelope fa" aria-hidden="true"></i></span>
	              <%= f.email_field :email, autofocus: true, class:'form-control', :placeholder => 'Enter Your Email' %>
	            </div>
	          </div>
	        </div>

	        <div class="form-group">
	          <%= f.label :password, class:'cols-sm-2 control-label' %>
	          <% if @minimum_password_length %>
	          <em>(<%= @minimum_password_length %> characters minimum)</em>
	          <% end %><br />
	          <div class="cols-sm-10">
	            <div class="input-group">
	              <span class="input-group-addon"><i class="fa fa-lock fa-lg" aria-hidden="true"></i></span>
	              <%= f.password_field :password, autocomplete: "off", class:'form-control', :placeholder => 'Enter Your Password' %>
	            </div>
	          </div>
	        </div>

	        <div class="form-group">
	          <%= f.label :password_confirmation, class:'cols-sm-2 label-control' %><br />
	            <div class="input-group">
	              <span class="input-group-addon"><i class="fa fa-lock fa-lg" aria-hidden="true"></i></span>
	              <%= f.password_field :password_confirmation, autocomplete: "off", class:'form-control' %>
	            </div>
	        </div>

	        <div class="form-group">
	          <%= f.submit "Sign up", class:'btn btn-primary btn-lg btn-block' %>
	        </div>
	      <% end %>
	      <div class="login-register">
	        <%= render "devise/shared/links" %>
	      </div>

	    </div>
	  </div>
	</div>

	<style>
	  .main{
	    margin-top: 20px;
	  }

	  h1.title {
	    font-size: 50px;
	    font-family: 'Passion One', cursive;
	    font-weight: 400;
	  }

	  hr{
	    width: 10%;
	    color: #fff;
	  }

	  .form-group{
	    margin-bottom: 15px;
	  }

	  label{
	    margin-bottom: 15px;
	  }

	  input,
	  input::-webkit-input-placeholder {
	    font-size: 11px;
	    padding-top: 3px;
	  }

	  .main-login{
	    background-color: #fff;
	    /* shadows and rounded borders */
	    -moz-border-radius: 2px;
	    -webkit-border-radius: 2px;
	    border-radius: 2px;
	    -moz-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.3);
	    -webkit-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.3);
	    box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.3);

	  }

	  .main-center{
	    margin-top: 30px;
	    margin: 0 auto;
	    max-width: 330px;
	    padding: 40px 40px;

	  }

	  .login-button{
	    margin-top: 5px;
	  }

	  .login-register{
	    font-size: 11px;
	    text-align: center;
	  }
	</style>

### Login

	<div class="container">
	  <div class="row main">
	    <div class="panel-heading">
	      <div class="panel-title text-center">
	        <h1 class="title">Log in</h1>
	        <hr />
	      </div>
	    </div>

	    <div class="main-login main-center">

	      <%= form_for(resource, as: resource_name, url: session_path(resource_name)) do |f| %>
	        <div class="form-group">
	          <%= f.label :email, "Your Email", class:"cols-sm-2 control-label" %><br />
	          <div class="cols-sm-10">
	            <div class="input-group">
	              <span class="input-group-addon"><i class="fa fa-envelope fa" aria-hidden="true"></i></span>
	              <%= f.email_field :email, autofocus: true, class:"form-control", :placeholder => "Enter Your Email" %>
	            </div>
	          </div>  
	        </div>

	        <div class="form-group">
	          <%= f.label :password, "Your Password", class:"cols-sm-2 control-label" %><br />
	          <div class="cols-sm-10">
	            <div class="input-group">
	              <span class="input-group-addon"><i class="fa fa-lock fa-lg" aria-hidden="true"></i></span>
	              <%= f.password_field :password, autocomplete: "off", class:"form-control", :placeholder => "Enter Your Password" %>
	            </div>  
	          </div>  
	        </div>

	        <% if devise_mapping.rememberable? -%>
	          <div class="field">
	            <%= f.check_box :remember_me %>
	            <%= f.label :remember_me %>
	          </div>
	        <% end -%>

	        <div class="actions">
	          <%= f.submit "Log in", class:"btn btn-primary btn-lg btn-block" %>
	        </div>
	      <% end %>
	      <br/>
	      <div class="login-register">
	        <%= render "devise/shared/links" %>
	      </div>
	    </div>
	  
	  </div>
	</div>  

	<style>
	  .main{
	    margin-top: 20px;
	  }

	  h1.title {
	    font-size: 50px;
	    font-family: 'Passion One', cursive;
	    font-weight: 400;
	  }

	  hr{
	    width: 10%;
	    color: #fff;
	  }

	  .form-group{
	    margin-bottom: 15px;
	  }

	  label{
	    margin-bottom: 15px;
	  }

	  input,
	  input::-webkit-input-placeholder {
	    font-size: 11px;
	    padding-top: 3px;
	  }

	  .main-login{
	    background-color: #fff;
	    /* shadows and rounded borders */
	    -moz-border-radius: 2px;
	    -webkit-border-radius: 2px;
	    border-radius: 2px;
	    -moz-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.3);
	    -webkit-box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.3);
	    box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.3);

	  }

	  .main-center{
	    margin-top: 30px;
	    margin: 0 auto;
	    max-width: 330px;
	    padding: 40px 40px;

	  }

	  .login-button{
	    margin-top: 5px;
	  }

	  .login-register{
	    font-size: 11px;
	    text-align: center;
	  }
	</style>
	
