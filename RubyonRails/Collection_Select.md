# collection_select

	<div class="field">
      <%= f.label :category_id %><br>
      <%= f.collection_select(:category_id, Category.all, :id, :name, class:'form-control') %>
    </div>