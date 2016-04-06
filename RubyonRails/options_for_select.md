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

## How to re-display form options_for_select in edit view, with the value from database

    <div class="field">
      <%= f.label :price, "Hourly Rate ($)" %>
      <%= f.select :price, options_for_select([['10',1], ['20',2], ['30',3], ['40',4], ['50',5], ['60',6], ['70',7], ['80',8], ['90',9], ['100',10]], @your_obj.price) %>
    </div>

    my actual code:

    <div>
        <%= f.label :active, 'List Aktif' %>
        <%= f.select(:active, options_for_select([
               ['Yes','1'],
               ['No','2']], @property.active),
               {:prompt => "Pilih.."},
               {class: "form-control"}
        ) %>
    </div>
