# Using serialize option in Ruby on Rails

How to make use of serialize option in Ruby on Rails so you can store information in your database more efficiently.

If you want to store an **array** or a **hash** as a value in a **table column**. Example you have an user model and each user have many tags :

	user.tags = "sports, science, engineer"

when retrieving the values

	tags = user.tags.split(",")

to get list of tags, we have to split the string value to get an array. And it is not comfortable.

Would be worse if store a **hash** as a value in a column. You have to **convert the hash into string** and then parse the string to get the hash every time you work with that column. 

### Better way! 

**Rails serialize option!** inside an ActiveRecord model, we can specify what kind of data are stored in a column, Rails would automatically take care of converting/parsing the actual values. Let's back to previous User model:

	class User < ActiveRecord::Base
	  serialize :tags, Array
	  serialize :course, Hash
	end

In this model, we have two columns: **tags** and **course**. We going to store an array into tags and a hash into courses. For example:

	user = User.new
	user.tags = ["sports", "science", "engineer"]
	user.tags # => ["sport", "science", "engineer"]

	user.course = {id: 1, name: "History"}
	user.course # => {id: 1, name: "History"}

**Please noted!** you should specify the correct data type you want to store so that you would 100% sure to retrieve the value back in correct data type (Rails use YAML by default to convert the data). 

In addition, you have to use **text data type** when creating this column in **migration** because Rails will convert all those object into **plain text** when storing in database. You can check it in your DBMS Tool and you will see how Rails do that.

You can read more [here](#serialize) or the web api is here: http://api.rubyonrails.org/classes/ActiveRecord/AttributeMethods/Serialization/ClassMethods.html

**Note**:

If you have serialized column in your model then this column will always be updated when you update your model, even though you make no changes to the values in that selialized column. So don't try to use this extensively in your app as it could affect the overall performance.

---

### Serialize

**serialize(attr_name, class_name_or_coder = Object) Link**

If you have an **attribute** needs to be saved to the database as an **object**, and **retrieved** as the same object, *then specify name of that attribute using this method and it will be handled automatically*. The serialization is done through YAML. If class_name is specified, **serialized object must be of that class on assignment and retrieval**. Otherwise **SerializationTypeMismatch** will be raised.

Empty objects as **{}**, in the case of Hash, or **[]**, in the case of **Array**, will always be **persisted** as null.

Keep in mind that database adapters handle certain serialization tasks for you. For instance: json and jsonb types in PostgreSQL will be converted between JSON object/array syntax and Ruby Hash or Array objects transparently. There is no need to use serialize in this case.

For more complex cases, such as conversion to or from your application domain objects, consider using the ActiveRecord::Attributes API.

**Parameters**

+ attr_name - The field name that should be serialized.

+ class_name_or_coder - Optional, a coder object, which responds to `.load` / `.dump` or a class name that the object type should be equal to.

Example

	# Serialize a preferences attribute.
	class User < ActiveRecord::Base
	  serialize :preferences
	end

	# Serialize preferences using JSON as coder.
	class User < ActiveRecord::Base
	  serialize :preferences, JSON
	end

	# Serialize preferences as Hash using YAML coder.
	class User < ActiveRecord::Base
	  serialize :preferences, Hash
	end

#### Error Produced 1

	ActiveRecord::SerializationTypeMismatch in BrandsController#update
	Attribute was supposed to be a Array, but was a Integer. -- 2

	Extracted source (around line #48):
	              
	  def update
	    respond_to do |format|
	      if @brand.update(brand_params)
	        format.html { redirect_to @brand, notice: 'Brand was successfully updated.' }
	        format.json { render :show, status: :ok, location: @brand }
	      else

Try change type integer tobe text

#### Error Produced 2

	ActiveRecord::SerializationTypeMismatch in BrandsController#update
	Attribute was supposed to be a Array, but was a String. -- "2"

