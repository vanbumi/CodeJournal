# Rails Options For Select and Bootstrap

	<div class="col-lg-3">
	    <%= f.label :location_cont, 'Property Location' %>
	    <%= f.select(:location_cont, options_for_select([
                                                        ['Cirebon','Cirebon'],
                                                        ['Batam','Batam'],
                                                        ['Sorong','Sorong']]),

                 {:prompt => "Any"},
                 {class: "form-control"}
        ) %>
  </div>

*Source*

	http://stackoverflow.com/questions/22111088/how-do-i-use-the-bootstrap-form-select-css-with-a-rails-model

	http://stackoverflow.com/questions/24339162/rails4-collection-select-with-data-options

*Acuan*

	<%= f.collection_select(:country_id, @countries, :id, :name, { :prompt => true, :selected => params[:country_id] }, { :class => 'select', :date => {:placeholder => 'Choose a Country...' }}) %>    