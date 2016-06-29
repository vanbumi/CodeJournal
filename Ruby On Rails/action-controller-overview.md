# Action Controller Overview

## Parameters

	class ClientsController < ApplicationController
	  # This action uses query string parameters because it gets run
	  # by an HTTP GET request, but this does not make any difference
	  # to the way in which the parameters are accessed. The URL for
	  # this action would look like this in order to list activated
	  # clients: /clients?status=activated
	  def index
	    if params[:status] == "activated"
	      @clients = Client.activated
	    else
	      @clients = Client.inactivated
	    end
	  end
	 
	  # This action uses POST parameters. They are most likely coming
	  # from an HTML form which the user has submitted. The URL for
	  # this RESTful request will be "/clients", and the data will be
	  # sent as part of the request body.
	  def create
	    @client = Client.new(params[:client])
	    if @client.save
	      redirect_to @client
	    else
	      # This line overrides the default rendering behavior, which
	      # would have been to render the "create" view.
	      render "new"
	    end
	  end
	end

### Routing Parameters

	get '/clients/:status' => 'clients#index', foo: 'bar'

### Strong Parameters

	class PeopleController < ActionController::Base
	  # This will raise an ActiveModel::ForbiddenAttributes exception
	  # because it's using mass assignment without an explicit permit
	  # step.
	  def create
	    Person.create(params[:person])
	  end
	 
	  # This will pass with flying colors as long as there's a person key
	  # in the parameters, otherwise it'll raise a
	  # ActionController::ParameterMissing exception, which will get
	  # caught by ActionController::Base and turned into that 400 Bad
	  # Request reply.
	  def update
	    person = current_account.people.find(params[:id])
	    person.update!(person_params)
	    redirect_to person
	  end
	 
	  private
	    # Using a private method to encapsulate the permissible parameters
	    # is just a good pattern since you'll be able to reuse the same
	    # permit list between create and update. Also, you can specialize
	    # this method with per-user checking of permissible attributes.
	    def person_params
	      params.require(:person).permit(:name, :age)
	    end
	end

#### Permitted Scalar Values

the key :id will pass the whitelisting if it appears in params and it has a permitted scalar value associated. Otherwise the key is going to be filtered out, so arrays, hashes, or any other objects cannot be injected.

The permitted scalar types are String, Symbol, NilClass, Numeric, TrueClass, FalseClass, Date, Time, DateTime, StringIO, IO, ActionDispatch::Http::UploadedFile and Rack::Test::UploadedFile.

To declare that the value in params must be an array of permitted scalar values map the key to an empty array:

	params.permit(:id)

## Session

### The Flash

The flash is a special part of the session which is cleared with each request. This means that values stored there will only be available in the next request, which is useful for passing error messages etc.

It is accessed in much the same way as the session, as a hash (it's a FlashHash instance).

Let's use the act of logging out as an example. The controller can send a message which will be displayed to the user on the next request:

	class LoginsController < ApplicationController
	  def destroy
	    session[:current_user_id] = nil
	    flash[:notice] = "You have successfully logged out."
	    redirect_to root_url
	  end
	end

Note that it is also possible to assign a flash message as part of the redirection. You can assign :notice, :alert or the general purpose :flash:

	redirect_to root_url, notice: "You have successfully logged out."
	redirect_to root_url, alert: "You're stuck here!"
	redirect_to root_url, flash: { referral_code: 1234 }	

## Filters

Filters are methods that are run before, after or "around" a controller action.

Filters are inherited, so if you set a filter on ApplicationController, it will be run on every controller in your application.

"Before" filters may halt the request cycle. A common "before" filter is one which requires that a user is logged in for an action to be run. You can define the filter method this way:
	
	class ApplicationController < ActionController::Base
	  before_action :require_login
	 
	  private
	 
	  def require_login
	    unless logged_in?
	      flash[:error] = "You must be logged in to access this section"
	      redirect_to new_login_url # halts request cycle
	    end
	  end
	end

