# Nice Sign Up & Login Form for Rails

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