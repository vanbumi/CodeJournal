# Rails-Angular Select Directive

	<div class="form-group" ng-model="nameCategory">
        <%= f.label :name %>
        <%= f.select(:name, options_for_select([
           ['Laser Film','Laser Film'],
           ['Kertas Kalkir','Kertas Kalkir'],
           ['Toner Spray','Toner Spray'],
           ['Inkjet Film','Inkjet Film'],
           ['Ink Meganano','Ink Meganano'],
           ['Master Paper','Master Paper'],
           ['Polyester Plate','Polyester Plate'],
           ['Master Plate (Plat Cetak) & Chemical','Master Plate (Plat Cetak) & Chemical'],
           ['Chromaline','Chromaline']], @category.name),

           {:prompt => "Pilih"},
           {class: "form-control", "ng-model" => "nameCategory"}
        ) %>
      </div>

      <div class="form-group" ng-show="nameCategory == 'Laser Film'">
        <%= f.label :merek %>
        <%= f.select(:merek, options_for_select([
          ['Vaneo','Vaneo'],
          ['Technova','Technova']], @category.merek),

         {:prompt => "Pilih"},
         {class: "form-control"}
         ) %>
      </div>

      <div class="form-group" ng-show="nameCategory == 'Kertas Kalkir'">
        <%= f.label :tipe %>
        <%= f.select(:tipe, options_for_select([
         ['Standar','Standar'],
         ['Inject','Inject']], @category.tipe),

         {:prompt => "Pilih"},
         {class: "form-control"}
            ) %>
    </div>