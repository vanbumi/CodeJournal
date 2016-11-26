# Current User & it Role

Basic

	<% if current_user.role.name == 'Master' || 'Owner' %>

Example

	<% if current_user.role.name == 'Master' || 'Owner' %>
	  <li><a href="/admin/users"><span class="glyphicon glyphicon-chevron-right"></span>&nbsp;&nbsp;User</a></li>
	  <li><a href="/admin/users"><span class="glyphicon glyphicon-chevron-right"></span>&nbsp;&nbsp;Karyawan</a></li>
	  <li><a href="/admin/roles"><span class="glyphicon glyphicon-chevron-right"></span>&nbsp;&nbsp;Role</a></li>
	  <li><a href="/admin/users/<%= current_user.id %>"><span class="glyphicon glyphicon-chevron-right"></span>&nbsp;&nbsp;Profile</a></li>
	<% else %>
	  <li><a href="/admin/users/<%= current_user.id %>"><span class="glyphicon glyphicon-chevron-right"></span>&nbsp;&nbsp;Profile</a></li>
	<% end %>
