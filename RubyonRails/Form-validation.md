# User input validation

	http://www.tutorialspoint.com/ruby-on-rails/rails-input-validations.htm

	http://api.rubyonrails.org/classes/ActiveModel/Validations/ClassMethods.html

##### validates_presence_of: 
The following checks that last_name and first_name should be filled and should not be NULL.

	validates_presence_of :firstname, :lastname

##### validates_length_of:
The following example shows various validations on a single field. These validations can be performed separately.

	validates_length_of :password,
	   :minimum => 8           # more than 8 characters
	   :maximum => 16          # shorter than 16 characters
	   :in => 8..16            # between 8 and 16 characters
	   :too_short => 'way too short'    
	   :too_long => 'way to long'

##### validates_acceptance_of:
The following will accept only 'Y' value for option field.

	validates_acceptance_of :option            
    	                    :accept => 'Y'

##### validates_confirmation_of:
The fields password and password_confirmation must match and will be used as follows

	validates_confirmation_of :password

##### validates_uniqueness_of:
The following puts a condition for user_name to be unique.

	validates_uniqueness_of :user_name

##### validates_format_of:
The following validates that a given email ID is in a valid format. This shows how you can use regular expression to validate a field.

	validates_format_of :email, :with => /\A([^@\s]+)@((?:[-a-z0-9]+\.)+[a-z]{2,})\Z/i, :on => :create   		    	                     	   

##### validates_numericality_of:
This validates that given field is numeric.

	validates_numericality_of   :value                 
	                            :only_integer => true   
	                            :allow_nil => true
	
	validates :nohp, numericality: { only_integer: true }                            

##### validates_inclusion_of:
The following checks that the passed value is an enumeration and falls in the given range.

	validates_inclusion_of  :gender,   
	                        :in => %w( m, f )

##### validates_exclusion_of
The following checks that the given values does not fall in the given range.

	validates_exclusion_of  :age        
	                        :in => 13..19

##### validates_inclusion_of
The following checks that the given values should fall in the given range. This is the opposite to validates_exclusion_of.

	validates_inclusion_of  :age
	                        :in => 13..19

##### validates_associated

	This validates that the associated object is valid.

##### Options for all Validations:
You can use the following options along with all the validations.

	:message => 'my own errormessage' Use this to print a custom error message in case of validation fails.

	:on => :create or :update This will be used in such cases where you want to perform validation only when record is being created or updated. So, if you use :create then this validation work only when there is a create operation on database.	                        	                                