# collection_select

	<div class="field">
      <%= f.label :category_id %><br>
      <%= f.collection_select(:category_id, Category.all, :id, :name, class:'form-control', :prompt => 'Pilih Category') %>
    </div>

# collection_select bootstrap

	<div class="form-group">
      <h3><span class="label label-primary">Informasi Kewilayahan</span></h3>
      <%= f.label :provinsi_id, "Nama Provinsi", class:"col-md-3 control-label text-right" %>
      <div class="col-md-9">
        <%= f.collection_select :provinsi_id, Provinsi.all, :id, :name, {prompt: "Select a Provinsi"}, {class: "form-control"} %>
        <span class="help-block">text helper</span>
        <br>
      </div>
    </div>

[Stack Overflow](http://stackoverflow.com/questions/18163621/rails-4-collection-select-not-inserting-class-attribute)        