# Devise form within a different controller

To get around this, you need to add the following methods to the helper class of the controller you wish to display the form under. Alternatively, you can just add them to your **application helper** to make them available anywhere.

	def resource_name
		:user
	end

	def resource
		@resource ||= User.new
	end

	def devise_mapping
		@devise_mapping ||= Devise.mappings[:user]
	end