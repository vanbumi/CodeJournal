# Rails Modal

* [how-to-add-bootstrap-modal-with-link-to-so-the-link-content-open-in-modal](http://stackoverflow.com/questions/15152486/how-to-add-bootstrap-modal-with-link-to-so-the-link-content-open-in-modal)

* [how to display a form inside a Bootstrap modal in Rails using JS views](https://github.com/germanescobar/rails-bootstrap-modal)

#### Bootstrap Modals allows you to display any content in a dynamic dialog prompts with minimum required functionality.[ajax-bootstrap-modals-rails](http://www.benkirane.ch/ajax-bootstrap-modals-rails/)

#### Get practise quickly

	rails generate resource Customer first_name last_name phone email street zip city

Add some Customers data to db/seeds.rb	

	Customer.destroy_all
	 
	Customer.create!([
	    {
	    	id: 1, first_name: "John", last_name: "Doe", email: "john@doe.com",
	        street: "Allen St.", city: "Manhattan", zip: "10002"
	     },
	     {
	    	id: 2, first_name: "Jane", last_name: "Roe", email: "jane@roe.com",
	        street: "Boo St.", city: "Kirkland", zip: "98034"
	    },
	    {
	    	id: 3, first_name: "Foo", last_name: "Bar", email: "foo@bar.com",
	        street: "Boo St.", city: "Kirkland", zip: "98034"
	    },
	    {
	    	id: 4, first_name: "Rachid", last_name: "Benkirane", email: "contact@roe.com", 
	        street: "Boo St.", city: "Kirkland",zip: "98034"
	    }
	 ])
	 
	p "Created #{Customer.count} customers."

Run db:migrate

	rake db:migrate

	rake db:seed 

adding some validations and an address method, our model should look like this:

	validates :first_name, presence: true, length: { minimum: 2 }
	validates :last_name, presence:true, length: {minimum: 2}
	 
	def address
		"#{street} #{zip} #{city}"
	end

routes.rb:

	resources :customers, path:  'admin/customers'

Next, we’ll add the CRUD actions to the customers controller:

	class CustomersController < ApplicationController

	  before_action :set_customer, only: [:show, :edit, :update, :destroy]
	  
	  def index
	    @customers = Customer.all
	  end

	  def show
	  end

	  def new
	    @customer = Customer.new
	  end

	  def create
	    @customer = Customer.create(customer_params)

	    respond_to do |format|
	      if @customer.save
	        format.json { head :no_content }
	        format.js
	      else
	        format.json { render json: @customer.errors.full_messages, 
	                            status: :unprocessable_entity }
	      end
	      
	    end
	  end

	  def edit
	  end

	  def update
	     respond_to do |format|
	      if @customer.update(customer_params)
	        format.json { head :no_content }
	        format.js
	      else
	        format.json { render json: @customer.errors.full_messages,
	                                   status: :unprocessable_entity }
	      end
	     
	    end
	  end


	  def destroy

	    @customer.destroy
	    respond_to do |format|
	      format.js
	      format.html { redirect_to posts_url }
	      format.json { head :no_content }
	    end
	  end

	private
	  
	  def set_customer
	  	@customer = Customer.find(params[:id])
	  end
	  
	  def customer_params
	    params.require(:customer).permit(:first_name, :last_name, 
	                            :phone, :email, :street, :zip, :city)
	  end

	end	

Views

Now let’s create a customers **index**.html.erb file:


	<div class="container">

	  <h2>Customers</h2>
	  <div class="well">
	    <%= link_to "New Customer", new_customer_path, remote: true, class: "btn btn-primary" %>
	  </div>
	  <div class="new-customer"></div>

	  <table id class="table table-bordered table-striped">
	    <thead>
	    <tr>
	      <th>First name</th>
	      <th>Last name</th>
	      <th>Email</th>
	      <th>Address</th>
	      <th>Actions</th>
	    </tr>
	    </thead>
	    <tbody id="customers">
	    <%= render @customers %>
	    </tbody>
	  </table>

	  <%= render 'dialog' %>

	</div>	

In **remote: true** tells Rails to use AJAX when creating a new customer, which allows the web page to send requests asynchronously to the server without leaving the page.
In line 20 and 24: we’ll use partial views to render the modal dynamic dialog and the customers rows.

Next, we’ll create a partial view for customers:

app/views/customers/_customer.html.erb

	<tr id="customer_<%= customer.id %>">
	  <td><%= customer.first_name %></td>
	  <td><%= customer.last_name %></td>
	  <td><%= customer.email %></td>
	  <td><%= customer.address %></td>
	  <td>
	    <%= link_to 'Edit', edit_customer_path(customer), remote: true, :class => 'btn btn-sm btn-info' %>
	    <%= link_to 'Delete', customer, remote: true, :method => :delete, data: {confirm: "Delete Customer: #{customer.first_name} #{customer.last_name}"}, :class => 'btn btn-sm btn-danger' %>
	  </td>
	</tr>

Next, we’ll add partial view for our **dynamic modal dialog**:

app/views/cusomers/_dialog.html.erb

	<div class="modal fade"
	           id="dialog" tabindex="-1" role="dialog" 
	           aria-labelledby="myModalLabel"
	           aria-hidden="true" 
	           data-backdrop="static" 
	           data-keyboard="true">
	  <div class="modal-dialog">
	    <div class="modal-content">
	      <div class="modal-header">
	        <button type="button" class="close" 
	                data-dismiss="modal" 
	                aria-label="Close">
	                <span aria-hidden="true">&times;</span></button>
	        <h3 class="modal-title"></h3>
	      </div>
	      <div class="modal-body">
	      </div>
	     
	    </div><!-- /.modal-content -->
	  </div><!-- /.modal-dialog -->
	</div><!-- /.modal -->

 now let’s set up the forms, that is used for creating and editing our customers. We’ll create a _form.html.erb partial:

 app/views/cusomers/_form.html.erb:

	<%= form_for(@customer, remote: true, :html => { :role => "form" }) do |f| %>
	<div id="error_explanation" class="bg-danger text-danger">
	</div>

	<div class="row">
	 <div class="col-sm-6">
	  <div class="form-group">
	    <%= f.label :first_name, :class => "control-label" %>
	    <%= f.text_field :first_name, :class => "form-control first_input"  %>
	  </div>
	  <div class="form-group">
	    <%= f.label :last_name, :class => "control-label" %>
	    <%= f.text_field :last_name, :class => "form-control" %>
	  </div>
	  <div class="form-group">
	    <%= f.label :phone, :class => "control-label" %>
	    <%= f.text_field :phone, :class => "form-control" %>
	  </div>
	  <div class="form-group">
	    <%= f.label :email, :class => "control-label" %>
	    <%= f.text_field :email, :class => "form-control" %>
	  </div>
	</div>

	<div class="col-sm-6">
	  <div class="form-group">
	    <%= f.label :street, :class => "control-label" %>
	    <%= f.text_field :street, :class => "form-control" %>
	  </div>
	  <div class="form-group">
	    <%= f.label :zip, :class => "control-label" %>
	    <%= f.text_field :zip, :class => "form-control" %>
	  </div>
	  <div class="form-group">
	    <%= f.label :city, :class => "control-label" %>
	    <%= f.text_field :city, :class => "form-control" %>
	  </div>
	  <div class="form-group">
	    <%= f.submit  @customer.new_record? ? "Create Create" : "Update Customer", :class => "btn btn-primary" %>
	  </div>
	</div>
	</div>
	<% end %>

** AJAX Bootstrap Modals**

In the case of an **Ajax request**, **Rails automatically calls a .js.erb file with the same name as the action**. So, let’s create this files.

We’ll begin with the **new action**:	

app/views/customers/new.js.erb

	// Add the dialog title
	$('#dialog h3').html("<i class='glyphicon glyphicon-plus'></i> Add New Customer");

	// Render the new form
	$('.modal-body').html('<%= j render("form") %>');

	// Show the dynamic dialog
	$('#dialog').modal("show");

	// Set focus to the first element
	$('#dialog').on('shown.bs.modal', function () {
		  $('.first_input').focus()
	  })	
				
Now let’s do the same thing for edit.js.erb:

app/views/cusomers/edit.js.erb

	// Add the dialog title
	$('#dialog h3').html("<i class=' glyphicon glyphicon-pencil'></i> Edit Customer");

	// Render the edit form
	$('.modal-body').html('<%= j render("form") %>');

	// Show the dynamic dialog
	$('#dialog').modal("show");

	// Set focus to the first element
	$('#dialog').on('shown.bs.modal', function () {
		  $('.first_input').focus()
	  })

Next, we’ll create the create.js.erb file:

app/views/cusomers/create.js.erb

	$('#dialog').modal('toggle');
	$('#customers').append('<%= j render (@customer) %>')

Next, we’ll add the update.js.erb file:

app/views/cusomers/update.js.erb

	$('#dialog').modal('toggle');
	$('#customer_<%= @customer.id %>').replaceWith('<%= j render (@customer) %>')

Finally, we’ll create the destroy.js.erb file:

app/views/cusomers/destroy.js.erb

	$('#customer_<%= @customer.id %>').fadeOut();


** To handle the validation errors we’ll add a javascript function in application.js**:

app/assets/javascripts/application.js

	$(document).ajaxError(function(event,xhr,options,exc) {
	    
	    var errors = JSON.parse(xhr.responseText);
	    var er ="<ul>";
	    for(var i = 0; i < errors.length; i++){
	        var list = errors[i];
	        er += "<li>"+list+"</li>"
	    }
	    er+="</ul>"
	    $("#error_explanation").html(er);
	       
	});

#### Custom Confirmation Alert

The confirmation dialog that appears when deleting a customer is the browser’s default. To custom this dialog to use Bootstrap, we’ll add some coffeescript in customers.coffe (Solution found in [Stackoverflow](http://stackoverflow.com/questions/26289601/rails-4-1-4-custom-confirmation-alert)).	

app/assets/javascripts/customers.coffee

	$ ->
	  $.rails.allowAction = (link) ->
	    return true unless link.attr('data-confirm')
	    $.rails.showConfirmDialog(link) 
	    false 

	  $.rails.confirmed = (link) ->
	    link.removeAttr('data-confirm')
	    link.trigger('click.rails')

	  $.rails.showConfirmDialog = (link) ->
	    message = link.attr 'data-confirm'
	    html = """
	           <div class="modal fade" id="confirmationDialog">
	             <div class="modal-dialog">
	               <div class="modal-content">
	                 <div class="modal-header">
	                   <a class="close" data-dismiss="modal">×</a>
	                   <h4><i class="glyphicon glyphicon-trash"></i>  #{message}</h4>
	                 </div>
	                 <div class="modal-footer">
	                   <a data-dismiss="modal" class="btn">Cancel</a>
	                   <a data-dismiss="modal" class="btn btn-danger confirm">Ok</a>
	                 </div>
	               </div>
	             </div>
	           </div>
	           """
	    $(html).modal('show')
	    $('#confirmationDialog .confirm').on 'click', -> $.rails.confirmed(link)

The full example code can be found at:[Github](https://github.com/benkirane/micro_crm)


















