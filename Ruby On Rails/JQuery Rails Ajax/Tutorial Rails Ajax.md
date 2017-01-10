# Tutorial Rails Ajax

Steps

...

### 8.1 Edit Row on the index

**Link to Edit, Remote: true**

	<td><%= link_to 'Edit', edit_koman_path(koman), remote: true %></td>

**Create new file, edit.js.erb**

render the form

	$(".new_one").hide().after("<%= j render 'form' %>");

To avoid repeating render form every clicking edit add :

	--> $(".edit_koman").remove();
		$(".new_one").hide().after("<%= j render 'form' %>");

![Inspect Element](http://res.cloudinary.com/medio/image/upload/v1483437777/edit_koman_cvf3jz.png)

And update like below:

	$(function(){

		$(".edit_koman").remove();
		$(".new_one").hide().after("<%= j render 'form' %>");

		$("tr").find("td:first").each(function(){
				if ($(this).text() == ("<%= raw @koman.name %>")) {
					$(this).parent().addClass("edit_row");
				}
			});
	});


### 8.2 - 8.3 

Add this to remove previous class in previous row

	$("tr").removeClass("edit_row")

edit.js.erb shoul be like below:

	$(function(){
		$(".edit_koman").remove();
		$(".new_koman").remove();
		$("tr").removeClass("edit_row")
		$(".new_one").hide().after("<%= j render 'form' %>");

		$("tr").find("td:first").each(function(){
				if ($(this).text() == ("<%= raw @koman.name %>")) {
					// alert("<%= raw @koman.name %>");
					$(this).parent().addClass("edit_row");
				}
			});
	});

**Add format.js in controller update**

	def update
	    respond_to do |format|
	      if @koman.update(koman_params)
	        format.html { redirect_to @koman, notice: 'Koman was successfully updated.' }
	        format.json { render :show, status: :ok, location: @koman }
	    --> format.js
	      else
	        format.html { render :edit }
	        format.json { render json: @koman.errors, status: :unprocessable_entity }
	    --> format.js
	      end
	    end
	end

**Create new fil update.js.erb**

Add below to remove the form after edit

	$(".edit_koman").remove();
	$(".new_one").show();

	$(".edit_row").find('td:first').text('<%= raw @koman.name %>').next().text("<%= raw @koman.comment %>");
	$("tr").removeClass('edit_row'); // to remove class css	after updating

### 9. Delete row from index list

**Add remote: true**

	<td>
		<%= link_to 'Destroy', koman, method: :delete, data: { confirm: 'Are you sure?' }, remote: true %>
	</td>

**Add format.js**

	def destroy
	    @koman.destroy
	    respond_to do |format|
	      format.html { redirect_to komen_url, notice: 'Koman was successfully destroyed.' }
	      format.json { head :no_content }
	      format.js
	    end
	end

**Create new file destroy.js.erb**

	$('tr').find('td:first').each(function(){
		if ($(this).text() == ('<%= raw @koman.name %>')) {
			$(this).parent().remove();
		}
	});

done

		