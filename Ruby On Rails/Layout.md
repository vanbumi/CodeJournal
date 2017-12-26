# How to not inlude layout in one controller
	
	class SayController < ApplicationController

		  layout false

		  def hello
		  end

		  def goodbye
		  end
	end

More read here [http://guides.rubyonrails.org/layouts_and_rendering.html](http://guides.rubyonrails.org/layouts_and_rendering.html)	