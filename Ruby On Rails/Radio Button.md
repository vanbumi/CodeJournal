## Radio Button

	<div class="form-group">
		<h4>Ketersedian data peta Drainase</h4>
	  	<%= f.label :peta_drainase, "Peta Drainase", class:"col-md-3 control-label text-right" %>
	  	<%= f.radio_button :peta_drainase, 'ada' %> 
	  	<%= label :peta_drainase, 'Ada' %>&nbsp;&nbsp;
	  	<%= f.radio_button :peta_drainase, 'tidak' %>
	  	<%= label :peta_drainase, 'Tidak' %>
	</div>

Or

	<% form_for(@message) do |f| %>
	  <%= f.radio_button :contactmethod, 'email' %> 
	  <%= f.label :contactmethod, 'Email', :value => 'email' %>
	  <%= f.radio_button :contactmethod, 'sms' %>
	  <%= f.label :contactmethod, 'SMS', :value => 'sms' %>
	<% end %>

I use first one

Ref : [Stack overflow](http://stackoverflow.com/questions/746387/labels-for-radio-buttons-in-rails-form)

