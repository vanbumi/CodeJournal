# How to not inlude layout in one controller
	
	class SayController < ApplicationController

		  layout false

		  def hello
		  end

		  def goodbye
		  end
	end