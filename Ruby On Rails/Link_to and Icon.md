# Rails link_to and icon integration

## Sample 1

	<%= link_to user_path(@user) do %>
	  <i class="icon-ok icon-white"></i> Do it@
	<% end %>

## Sample 2

	<%= link_to destroy_user_session_path do %>
        <i class="fa fa-ban fa-fw pull-right"></i>Logout
    <% end %>

Result something like this

![link_to plus icon](http://res.cloudinary.com/medio/image/upload/v1471970830/result_vldi09.png)

## Sample 3

	<a href="/admin/login.php.html" data-toggle="tooltip" data-placement="bottom" title="Logout"><i class="gi gi-exit"></i></a>

Convert into below:

	<%= link_to destroy_user_session_path do %>
        <i class="gi gi-exit"></i>
    <% end %>

## Sample 4

	<%= link_to new_drainase_path do %>
	    <span class="btn btn-primary"><i class="fa fa-plus"></i>&nbsp;Data Baru</span>
	<% end %>    	     	