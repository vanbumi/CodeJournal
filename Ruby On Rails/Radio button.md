# Radio button on Rails	

### Case for DearMom 

	<div class="field">
	    <%= f.label :active, 'Aktifkan Category?', class:'control-label' %>&nbsp;&nbsp;
	    <%= f.radio_button :active, 'active', :checked => true %> 
	    <%= label :aktifkan_ya, 'Ya' %>&nbsp;
	    <%= f.radio_button :active, 'not active' %>
	    <%= label :aktifkan_tidak, 'Tidak' %>
	</div>