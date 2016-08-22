
## For User Controller

	# Never trust parameters from the scary internet, only allow the white list through.
    
    def user_params
      # params[:user]
      params.require(:user).permit(:name)
    end