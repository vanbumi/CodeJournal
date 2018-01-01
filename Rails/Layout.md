## How to not inlude layout in one controller
	
	class SayController < ApplicationController

		  layout false

		  def hello
		  end

		  def goodbye
		  end
	end

More read here [http://guides.rubyonrails.org/layouts_and_rendering.html](http://guides.rubyonrails.org/layouts_and_rendering.html)	


## Different layout for different Actions

	class MyController < ApplicationController
		layout :resolve_layout

		# ...

		private

		def resolve_layout
			case action_name
			when "new", "create"
				"some_layout"
			when "index"
				"other_layout"
			else
				"application"
			end
		end
	end