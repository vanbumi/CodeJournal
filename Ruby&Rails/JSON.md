# To format json

	respond_to do |format|
      format.html
      format.json { render :json => @categories }
    end
