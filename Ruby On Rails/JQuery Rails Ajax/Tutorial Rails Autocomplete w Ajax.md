# Rails Autocomplete with Ajax

original file latihan ~/sites_jq/latihan$ => sites/latihan/jq/latihan

## Lesson 1

Get example google search

Create new app

	rails new rails_autocomplete

Generate scaffold customer

	rails g scaffold customer name address:text

Create scaffold data

	rails g controller data enter search

Cek url 

	$rake routes
	
Path			Method	URI
-------------------------------------------------------------------------						
data_enter		GET    	/data/enter(.:format) 		data#enter

data_search 	GET    	/data/search(.:format)      data#search
	
Perhatikan methode GET pada ke duanya

Start server:

	rails s		

Cek controller

	class DataController < ApplicationController
	  def enter
	  end

	  def search
	  end
	end

Cek view > data > enter.html.erb 
	view > data > search.html.erb

Edit data > enter, like below:

	<h1>Search here</h1>
	<%= form_tag data_search_path do %>
		<%= text_field_tag :search, '', size:25 %>
		<%= submit_tag 'Search', :id => 'search_key' %>	
	<% end %>

Cek at localhost:3000/data/enter

Cek form dengan inspect element

	<form action="/data/search" accept-charset="UTF-8" method="post">
		<input name="utf8" value="✓" type="hidden"><input name="authenticity_token" value="NcF5AlW+9SAZoDYbXxr77inbaAbnGnYaE0UaaHRH2CUUI0TbEUprQ66fY823FjQvAD6MJx+ZwGK5XGeEsO+myw==" type="hidden">
		<input name="search" id="search" value="" size="25" type="text">
		<input name="commit" value="Search" id="search_key" data-disable-with="Search" type="submit">
	</form>

Perhatikan action URI nya
Perhatikan input nya -> value search	

Secara default form akan di generate dengan method POST. Sedangkan di routes method nya adalah GET. 

Coba klik submit maka di kirim ke halaman lain dengan method POST.

Maka form di atas kita update dengan method: 'GET', method:'GET'

	<%= form_tag data_search_path, method:'GET' do %>
		<%= text_field_tag :search, '', size:25 %>
		<%= submit_tag 'Search', :id => 'search_key' %>	
	<% end %>

Refresh halaman & Cek lagi dengan inspect element maka akan berubah menjadi method GET.

	<form action="/data/search" accept-charset="UTF-8" method="get">
		<input name="utf8" value="✓" type="hidden">
		<input name="search" id="search" value="" size="25" type="text">
		<input name="commit" value="Search" id="search_key" data-disable-with="Search" type="submit">
	</form>	

Bila kita click search maka di browser akan tertulis seperti ini:

	http://localhost:3000/data/search?utf8=%E2%9C%93&search=&commit=Search

Dan pada terminal akan tertulis seperti ini:

	Started GET "/data/search?utf8=%E2%9C%93&search=&commit=Search" for 127.0.0.1 at 2017-01-09 13:48:44 +0700
	Processing by DataController#search as HTML
	  Parameters: {"utf8"=>"✓", "search"=>"", "commit"=>"Search"}
	  Rendering data/search.html.erb within layouts/application
	  Rendered data/search.html.erb within layouts/application (0.6ms)
	Completed 200 OK in 64ms (Views: 62.7ms | ActiveRecord: 0.0ms)

Perhatikan parameter search => kosong, bila kita search dyo dan klik search

Di browser:

	http://localhost:3000/data/search?utf8=%E2%9C%93&search=Dyo&commit=Search

Di terminal: 

	Started GET "/data/search?utf8=%E2%9C%93&search=Dyo&commit=Search" for 127.0.0.1 at 2017-01-09 13:53:52 +0700
	Processing by DataController#search as HTML
	  Parameters: {"utf8"=>"✓", "search"=>"Ali", "commit"=>"Search"}
	  Rendering data/search.html.erb within layouts/application
	  Rendered data/search.html.erb within layouts/application (0.4ms)
	Completed 200 OK in 69ms (Views: 67.9ms | ActiveRecord: 0.0ms)

Untuk menghilangkan autocomplete yang dibuat oleh browser cookies, tambahkan di field input:

	:autocomplete => :off

Cek kembali di inspect element, autocomplete off.
Dan cek di form search pastikan autocomplete cookies sudah tidak ada lagi.	

Tambahkan remote true di form untuk menggunakan ajax.

	remote: true

Akan menjadi seperti dibawah ini:

	<%= form_tag data_search_path, method: 'GET', remote: true do %>
		<%= text_field_tag :search, '', size:25, :autocomplete => 'off' %>
		<%= submit_tag 'Search', :id => 'search_key' %>
	<% end %>	

Apabila kita click search maka tidak akan pindah halaman lagi. Karena search akan ditangani oleh Ajax.

Bila kita lihat log di terminal maka, search as JS:

	Started GET "/data/search?utf8=%E2%9C%93&search=&commit=Search" for 127.0.0.1 at 2017-01-09 14:14:54 +0700
	Processing by DataController#search as JS
	  Parameters: {"utf8"=>"✓", "search"=>"", "commit"=>"Search"}
	  Rendering data/search.html.erb within layouts/application
	  Rendered data/search.html.erb within layouts/application (0.5ms)
	Completed 200 OK in 61ms (Views: 57.2ms | ActiveRecord: 0.0ms)

Perhatikan pada: Processing by DataController#search as JS.

Maka buat file baru search.js.erb, yang akan menangani search request tsb. Dalama Rails ...js.erb

Kita test dengan alert:

	alert("Hello from search.js.erb!")

![search](http://res.cloudinary.com/medioxtra/image/upload/v1483946451/Screenshot_from_2017-01-09_14_19_49_ffu1e0.png)

---

## Lesson 2

Cek jQueryUI [autocomplete](https://jqueryui.com/autocomplete/)

Click view source:

Download source nya yang ada disitu:

	<link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
	<link rel="stylesheet" href="/resources/demos/style.css">
	<script src="https://code.jquery.com/jquery-1.12.4.js"></script>
	<script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>

Dengan cara copy link di layout > applications.html.erb

 	<!-- autocomplete -->
    <link rel="stylesheet" href="//code.jquery.com/ui/1.12.1/themes/base/jquery-ui.css">
    <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
    <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>

copy ini ke file search.js.erb

	$( function() {
	  var availableTags = [
	  "ActionScript",
	  "AppleScript",
	  "Asp",
	  "BASIC",
	  "C",
	  "C++",
	  "Clojure",
	  "COBOL",
	  "ColdFusion",
	  "Erlang",
	  "Fortran",
	  "Groovy",
	  "Haskell",
	  "Java",
	  "JavaScript",
	  "Lisp",
	  "Perl",
	  "PHP",
	  "Python",
	  "Ruby",
	  "Scala",
	  "Scheme"
	  ];
	  $( "#search" ).autocomplete({
	  source: availableTags
	  });
	} );

Kemudian test di browser, pada search awali tekan enter dulu (sementara).	

Coba rubah spt ini:

$( function() {
	  var availableTags = ['Brandon', 'Ersya', 'Dyo'];
	  $( "#search" ).autocomplete({
	  source: availableTags
	  });
	} );

Coba di browser

Tambahkan user baru: Kasper

Test di browser	

Untuk mengambil data dari database, modif file search.js.erb menjadi

	$( function() {
	  var availableTags = <%= raw @auto %>;
	  $( "#search" ).autocomplete({
	  source: availableTags
	  });
	} );

Untuk mengambil data dari database gunakan:

	<%= raw @auto %>

dimana instan variable @auto di inisiasi di controler.		

Tambahkan instant variable @ auto di controller search: 

	def search
	    @auto = [
	      "ActionScript",
	      "AppleScript",
	      "Asp",
	      "BASIC",
	      "C",
	      "C++",
	      "Clojure",
	      "COBOL",
	      "ColdFusion",
	      "Erlang",
	      "Fortran",
	      "Groovy",
	      "Haskell",
	      "Java",
	      "JavaScript",
	      "Lisp",
	      "Perl",
	      "PHP",
	      "Python",
	      "Ruby",
	      "Scala",
	      "Scheme"
	    ]
	end

Atau modif lagi:

	def search
		@auto = ['Brandon', 'Ersya', 'Dyo']
	end	

Kemudian cek di browser, akan sama hasilnya.

Modif di controller agar dapat mengambil data dari **database**.

	def search 
		query = params[:search]
	end

:search ini ambil dari form :

	<input type="text" name="search" id="search" value="" size="25" autocomplete="off">	

Kemudian search di browser "brandon"	

dan cek paramameters nya lihat di terminal:

	Started GET "/search?utf8=%E2%9C%93&search=brandon&commit=Search" for 127.0.0.1 at 2017-03-09 19:30:13 +0700
	Processing by HomeController#search as JS
	  Parameters: {"utf8"=>"✓", "search"=>"brandon", "commit"=>"Search"}
	  Rendering home/search.js.erb
	  Rendered home/search.js.erb (0.7ms)
	Completed 200 OK in 22ms (Views: 11.6ms | ActiveRecord: 0.0ms)

	def search
		query ="%" + params[:search] + "%"
		@auto = Koman.where('name LIKE ?', query).pluck(:name)
	end

Dan coba di browser, search for "u" dan cek di terminal hasilnya sbb:

	Started GET "/search?utf8=%E2%9C%93&search=u&commit=search" for 127.0.0.1 at 2017-03-10 22:30:18 +0700
	Processing by HomeController#search as JS
	  Parameters: {"utf8"=>"✓", "search"=>"u", "commit"=>"search"}
	   (0.8ms)  SELECT "products"."name" FROM "products" WHERE (name Like '%u%')
	  Rendering home/search.js.erb
	  Rendered home/search.js.erb (0.9ms)
	Completed 200 OK in 16ms (Views: 7.7ms | ActiveRecord: 0.8ms)

Lihat parameternya:

Parameters: {"utf8"=>"✓", "search"=>"u", "commit"=>"search"}
(0.8ms)  SELECT "products"."name" FROM "products" WHERE (name Like '%u%')


![sukses](http://res.cloudinary.com/medioxtra/image/upload/v1483954360/sukses_ycbgat.png)	

Coba dengan menambahkan puts @auto.inspect

	def search
		query ="%" + params[:search] + "%"
		@auto = Koman.where('name LIKE ?', query).pluck(:name)
		puts @auto.inspect
	end

---

## Lesson 3

Tambahkan puts @auto.inspect untuk inspect di terminal

	def search
		query ="%" + params[:search] + "%"
		@auto = Koman.where('name LIKE ?', query).pluck(:name)
		puts @auto.inspect
	end

![inspek](http://res.cloudinary.com/medioxtra/image/upload/v1483959982/inspect_km16xv.png)

	Started GET "/data/search?utf8=%E2%9C%93&search=b&commit=Search" for 127.0.0.1 at 2017-01-09 18:07:05 +0700
	Processing by DataController#search as JS
	  Parameters: {"utf8"=>"✓", "search"=>"b", "commit"=>"Search"}
	   (0.3ms)  SELECT "komen"."name" FROM "komen" WHERE (name LIKE '%b%')
	["Brandon JB", "Dyo B"]
	  Rendering data/search.js.erb
	  Rendered data/search.js.erb (0.8ms)
	Completed 200 OK in 24ms (Views: 15.8ms | ActiveRecord: 0.3ms)

**pluck(*column_names) public**

Use pluck as a shortcut to select one or more attributes without loading a bunch of records just to grab the attributes you want.

	Person.pluck(:name)

instead of

	Person.all.map(&:name)

Tambahkan supaya tidak perlu di refresh dan di enter lagi, di assets/javascripts/application.js

	$(function(){
	  $('#search').on('keyup', function(){
	    $('#search_key').click();
	  });
	});

*Catatan karena sementara belum jalan, maka saya taruh di file **enter.html.erb** and works perfectly.

![](http://res.cloudinary.com/medioxtra/image/upload/c_scale,w_900/v1484012610/onkeyup_zw4qwl.png)

** *Catatan: Untuk mencegah input kosong atau spasi tambahkan variable dan condition:**

	$(function(){
	  $('#search').on('keyup', function(){
	  	var x = ( $('#search').val() ).trim();
	  	if (x.length > 0){
	    	$('#search_key').click();
	    }
	  });
	});

---

## Lesson 4

<<<<<<< HEAD
Inspeksi element kembali form input search :

	<input type="text" name="search" id="search" value="" size="25" autocomplete="off" class="form-control no-border ui-autocomplete-input"> 

class **ui-autocomplete** bisa di jadikan class style untuk menambahkan style:

	.ui-autocomplete {  
=======
Pada saat search cek di inspection:

	<input type="text" name="search" id="search" value="" size="25" autocomplete="off" class="form-control no-border ui-autocomplete-input">

Ambil class dari input form dan buat css nya:

	.ui-autocomplete-input {
>>>>>>> 224f29a9877392c3e4d9dabac636f0e56e685b72
		height: 100px;
		overflow-y: scroll;
		overflow-x: hidden;
	}

<<<<<<< HEAD
Membuat function select

$(function(){
	$("#search").autocomplete({select: function(event, ui){
=======
Next membuat function selected :

$(function(){
	$('#search').autocomplete({select: function(event, ui){
>>>>>>> 224f29a9877392c3e4d9dabac636f0e56e685b72
		alert(ui.item.value);
	}});
});

---

## Lesson 5

<<<<<<< HEAD
Add in application.html.erb or home index.html for placing result of selected search

	<div id="product_data"></div>

Update file search.js.erb below:

	$("#product_data").html("<%= j render 'data' %>");

Create new render file call _data.html.erb, fill with this below:

	<% unless @full.blank? %>
	    <p>
	        <%= raw @full.name %>
	    </p>
	    <p>
	        <%= raw @full.price_awal %>
	    </p>
	    <p>
	        <%= raw @full.price_sekarang %>
	    </p>
	<% end %>

Update application.js

	$(function(){
		$("#search").autocomplete({select: function(event, ui){
	        setTimeout(function(){
	            $('#search_key').click();
	            alert(ui.item.value);
	        }, 10);    
		}});
	});	

Test di browser

Success!

Update file _data.html.erb

	<% unless @full.blank? %>

	    <div class="row well">

	        <div class="col-sm-6 text-right">
	            <img src="http://res.cloudinary.com/dearmombabyshop/image/upload/v1486697984/stroller1_rc6jhp.jpg" alt="">
	        </div>

	        <div class="col-sm-6">
	            <h4><%= @full.name %></h4> <br>
	            <div id="price">
	                <div class="price-awal">Rp <%= @full.price_awal %></div>
	                <div class="price-sekarang">Rp <%= @full.price_sekarang %></div>
	            </div>
	            <br>
	            <div class="status">
	                <span class="label label-default"><%= @full.status %></span>
	            </div>
	            <br>    
	            <a class="btn btn-default" href="/show/<%= @full.id %>">Lihat</a>
	        </div>             
	     
	    </div>

	<% end %>


=======
>>>>>>> 224f29a9877392c3e4d9dabac636f0e56e685b72

