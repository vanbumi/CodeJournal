# Multiple Select

	<div class="form-group">
	    <label class="col-md-3 control-label" for="example-text-input"><%= f.label :multiple %></label>
	    <div class="col-md-9">
	      <%= f.select(:PartisipasiSwasta, [['Type A', 'Type A'],
	                                        ['Type B', 'Type B'],
	                                        ['Type C', 'Type C'],
	                                        ['Type D', 'Type D'],
	                                        ['Type E', 'Type E']
	      ],{ :prompt => "Please select"},
	                   { :multiple => true, :size => 5, class:'form-control' }
	          ) %>
	      <br>
	    </div>
	</div>