# Menggapai Meteor JS 
### Membangun Real-Time Web Aplikasi dengan JavaScript

### Apa itu Meteor?

Meteor adalah sebuah platform dibangun diatas Node.js untuk membuat website aplikasi secara real-time. Jadi antara aplikasi database dan user interface dipastikan keduanya selalu sinkronisasi.

### Kenapa Meteor?

Kenapa anda musti belajar Meteor dibanding web framework lainnya? ~~Kesampingkan semua macam fitur dari Meteor, yang kami yakini satu hal adalah:~~ Meteor cukup mudah untuk dipelajari.

Dengan asumsi anda familiar dengan dasar-dasar JavaScript sintaks dan konsepnya. Jika anda belum terbiasa dengan JavaScript, kami menyarankan untuk membaca terlebih dahulu buku ini sebelum memulai dengan meteor.

* [A JavaScript Primer For Meteor](https://www.discovermeteor.com/blog/javascript-for-meteor/)
* [Github Microscope](https://github.com/DiscoverMeteor/Microscope)

### Resources lainnya

Jika ingin belajar lebih lanjut, lebih khusus & spesifik tentang Meteor, [dokumentasi resmi Meteor](http://docs.meteor.com/) dan [Meteor Guide](http://guide.meteor.com/) adalah tempat terbaik untuk memulainya.

Kami juga merekomendasikan [Stack Overflow](https://webchat.freenode.net/) untuk pertanyaan, solusi pemecahan masalah.

### Git

Anda tidak harus sudah familiar dengan Git version control, tapi kami rekomendasikan untuk mulai mempelajari dan menggunakannya.

[Git Is Simpler Than You Think](http://nfarina.com/post/9868516270/git-is-simpler)

## Mulai disini

Install Meteor secara relatif cukup mudah, dalam banyak kasus anda sudah bisa menjalan Meteor hanya dengan waktu kurang dari 5 menit.

Mac OS or Linux

	curl https://install.meteor.com | sh

Cek versi:

	$ meteor --version
	~>	Meteor 1.4.2.3	


### Membuat aplikasi sederhana

Setelah berhasil menginstal Meteor kita bisa langsung membuat aplikasi, dengan baris perintah sbb :

	meteor create microscope

Perintah diatas akan mendownload Meteor dan setup dasar serta siap digunakan untuk proyek Meteor anda. Anda akan melihat direktori microscope/, berisi file dan direktori lain sbb:	

	client/
		main.css
		main.html
		main.js
	.gitignore
	.meteor/
	package.json
	server/
		main.js

Untuk menjalankan aplikasi, pada terminal anda ketikkan sbb:

	cd microscope
	meteor		

Buka browser anda di http://localhost:3000/

### Error!

	Your app is crashing. Here's the latest log:
	/home/dyo/sites_meteor/microscope/.meteor/local/build/programs/server/boot.js:348
	}).run();
	   ^

	Error: The babel-runtime npm package could not be found in your node_modules 
	directory. Please run the following command to install it:

	  meteor npm install --save babel-runtime

	    at meteorInstall.node_modules.meteor.babel-runtime.babel-runtime.js (packages/babel-runtime.js:37:9)
	    at fileEvaluate (packages/modules-runtime.js:181:9)
	    at require (packages/modules-runtime.js:106:16)
	    at packages/babel-runtime.js:139:15
	    at packages/babel-runtime.js:150:3
	    at /home/dyo/sites_meteor/microscope/.meteor/local/build/programs/server/boot.js:295:34
	    at Array.forEach (native)
	    at Function._.each._.forEach (/home/dyo/.meteor/packages/meteor-tool/.1.4.2_3.mea2r9++os.linux.x86_32+web.browser+web.cordova/mt-os.linux.x86_32/dev_bundle/server-lib/node_modules/underscore/underscore.js:79:11)
	    at /home/dyo/sites_meteor/microscope/.meteor/local/build/programs/server/boot.js:128:5
	    at /home/dyo/sites_meteor/microscope/.meteor/local/build/programs/server/boot.js:344:5
	Exited with code: 1
	Your application is crashing. Waiting for file change.

Coba jalankan perintah:

	meteor npm install --save babel-runtime

Buka kembali http://localhost:3000/

![welcome](http://res.cloudinary.com/medioxtra/image/upload/v1481200587/welcomemeteor_oylfmi.png)

### Menambahkan sebuah Package

Kita akan menggunakan Meteor sistim package untuk menambahkan Bootstrap framework kedalam proyek kita.

	meteor add twbs:bootstrap

Hasilnya:

	Changes to your project's package version selections:	                   twbs:bootstrap  added, version 3.3.6          
	twbs:bootstrap: The most popular front-end framework for developing responsive,
	mobile first projects on the web.

Tambahkan juga Session package:

	meteor add session

Untuk melihat daftar package yang digunakan, buka file packages di folder .meteor:

	# Meteor packages used by this project, one per line.
	# Check this file (and the other files in this directory) into your repository.
	#
	# 'meteor add' and 'meteor remove' will edit this file for you,
	# but you can also edit it by hand.

	meteor-base@1.0.4             # Packages every Meteor app needs to have
	mobile-experience@1.0.4       # Packages for a great mobile UX
	mongo@1.1.14                   # The database Meteor supports right now
	blaze-html-templates@1.0.4 # Compile .html files into Meteor Blaze views
	reactive-var@1.0.11            # Reactive variable for tracker
	jquery@1.11.10                  # Helpful client-side library
	tracker@1.1.1                 # Meteor's client-side reactive programming library

	standard-minifier-css@1.3.2   # CSS minifier run for production mode
	standard-minifier-js@1.2.1    # JS minifier run for production mode
	es5-shim@4.6.15                # ECMAScript 5 compatibility for older browsers.
	ecmascript@0.6.1              # Enable ECMAScript2015+ syntax in app code
	shell-server@0.2.1            # Server-side component of the `meteor shell` command

	autopublish@1.0.7             # Publish all data to the clients (for prototyping)
	insecure@1.0.7                # Allow all DB writes from clients (for prototyping)
	twbs:bootstrap
	session

Pastikan twbs:bootstrap package sudah ada di daftar packages.

### NPM Packages

Juga terdapat package.json file di repository:

	{
	  "name": "microscope",
	  "private": true,
	  "scripts": {
	    "start": "meteor run"
	  },
	  "dependencies": {
	    "babel-runtime": "^6.18.0",
	    "meteor-node-stubs": "~0.2.0"
	  }
	}	

File ini digunakan untuk memberitahu NPM (Node’s package manager) yang harus dilakukan, sama seperti file .meteor/packages memberitahu Meteor paket mana yang dijalankan. Satu kunci perbedaan antara kedua sistim packages adalah tidak sama seperti Meteor, NPM tidak otomatis mem-parse package.json file pada aplikasi. Jadi anda harus lakukan secara manual setiap **menambahkan atau menghapus sebuah NPM package**. 

Dengan melakukan sbb:

	npm install

> #### Catatan pada Packages
Packages pada konteks Meteor, ada hal spesifik. Meteor menggunakan lima dasar tipe packages:
- **Meteor-base package** stands alone: ini berisi **Meteor’s core components**,
Meteor app tidak dapat jalan tanpa ini.
- **First-party packages** datang bundled dengan Meteor. Beberapa seperti **mongo** atau
**session**, kemudian check atau http.
- **Local packages** adalah spesifik untuk aplikasi anda, dan berada di local **/packages** direktori.
- **Atmosphere packages** adalah kustom, third-party packages yang di publish ke **Atmosphere**, Meteor’s online package repository. Mereka semua mengikuti author:package naming  convention.
- Terakhir, **NPM packages** adalah Node.js packages. Tidak dapat dimasukan pada daftar package Meteor anda, tapi sebagai gantinya terdaftar di file **package.json**.

### File Struktur Aplikasi Meteor

Sebelum kita mulai menulis kode, kita harus setup file proyek dengan baik. Pastikan kita menjaga kerapihan kode dalam bekerja: 

* Buka direktori client dan server dan hapus isi dari file client/main.html serta isi dari file client/main.js seluruhnya.
* Buat dua root direktori baru didalam  /**microscope** : /public , dan /lib.

**Aturan di Meteor sbb**:

* Kode didalam /server direktori hanya berjalan di server.
* Kode didalam /client direktori hanya berjalan di client. 
* Selebihnya berjalan antara di client and server.
* Static assets (fonts, images, dll.) dimasukan di /public direktori.

Bagaimana Meteor memutuskan urutan file yang di load pertama kali:

* File didalam /lib adalah pertama di load (munculkan) sebelum yang lainnya.
* File-file seperti **main.*** di load setelah file yang lainnya.
* Yang lainnya di load dalam urutan alphabetical berdasarkan nama file nya.

> #### Catatan 
Pada direktori tersembunyi .meteor adalah berisi dimana Meteor menyimpan file-file nya secara pribadi, jangan merubah dan memodifikasi file-file tersebut karena akan mengakibatkan eror. Biarkan apa adanya, yang perlu dilihat hanya adalah direktori .meteor/packages dan .meteor/release yang berisi daftar smart packages dan versi Meteor yang digunakan. Pada saat anda menginstal package baru dan merubah Meteor releases, akan berguna sekali untuk mengecek perubahan yang terjadi pada file tersebut.

---

> #### Underscore atau CamelCase?
* Gunakan camelCase karena JavaScript menggunakannya! (ingat JavaScript, bukan java_script!).
* Gunakan Underscore untuk file name, ( my_file.js ).
* Gunakan hyphens untuk CSS classes ( .my-class ), hyphens ( font-family, text-align, dll.).

### CSS Style

Di Meteor, tidak seperti file static asset lainnya, pada Meteor di letakan di folder /**client**, buka di folder /**public**. Buatlah file client/stylesheets/style.css dan masukan kode seperti dibawah ini :

	.grid-block, .main, .post, .comments li, .comment-form {
	  background: #fff;
	  border-radius: 3px;
	  padding: 10px;
	  margin-bottom: 10px;
	  -webkit-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.15);
	  -moz-box-shadow: 0 1px 1px rgba(0, 0, 0, 0.15);
	  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.15);
	}
	body {
	  background: #eee;
	  color: #666666; }
	  #main {
	  position: relative;
	  }
	  .page {
	  position: absolute;
	  top: 0px;
	  width: 100%;
	  }
	  .navbar {
	  margin-bottom: 10px; }
	  /* line 32, ../sass/style.scss */
	  .navbar .navbar-inner {
	  border-radius: 0px 0px 3px 3px; }
	  #spinner {
	  height: 300px; }
	  .post {
	  /* For modern browsers */
	  /* For IE 6/7 (trigger hasLayout) */
	  *zoom: 1;
	  position: relative;
	  opacity: 1; }
	  .post:before, .post:after {
	  content: "";
	  display: table; }
	  .post:after {
	  clear: both; }
	  .post.invisible {
	  opacity: 0; }
	  .post.instant {
	  -webkit-transition: none;
	  -moz-transition: none;
	  -o-transition: none;
	  transition: none; }
	  .post.animate{
	  -webkit-transition: all 300ms 0ms;
	  -moz-transition: all 300ms 0ms ease-in;
	  -o-transition: all 300ms 0ms ease-in;
	  transition: all 300ms 0ms ease-in; }
	  .post .upvote {
	  display: block;
	  margin: 7px 12px 0 0;
	  float: left; }
	  .post .post-content {
	  float: left;
	}
	.post .post-content h3 {
	  margin: 0;
	  line-height: 1.4;
	  font-size: 18px; }
	  .post .post-content h3 a {
	  display: inline-block;
	  margin-right: 5px; }
	  .post .post-content h3 span {
	  font-weight: normal;
	  font-size: 14px;
	  display: inline-block;
	  color: #aaaaaa; }
	  .post .post-content p {
	  margin: 0; }
	  .post .discuss {
	  display: block;
	  float: right;
	  margin-top: 7px;
	}
	.comments {
	  list-style-type: none;
	  margin: 0; }
	  .comments li h4 {
	  font-size: 16px;
	  margin: 0; }
	  .comments li h4 .date {
	  font-size: 12px;
	  font-weight: normal; }
	  .comments li h4 a {
	  font-size: 12px; }
	  .comments li p:last-child {
	  margin-bottom: 0;
	}
	.dropdown-menu span {
	  display: block;
	  padding: 3px 20px;
	  clear: both;
	  line-height: 20px;
	  color: #bbb;
	  white-space: nowrap;
	}
	.load-more {
	  display: block;
	  border-radius: 3px;
	  background: rgba(0, 0, 0, 0.05);
	  text-align: center;
	  height: 60px;
	  line-height: 60px;
	  margin-bottom: 10px;
	}
	.load-more:hover {
	  text-decoration: none;
	  background: rgba(0, 0, 0, 0.1); }
	  .posts .spinner-container{
	  position: relative;
	  height: 100px;
	}
	.jumbotron{
	  text-align: center;
	}
	.jumbotron h2{
	  font-size: 60px;
	  font-weight: 100;
	}
	@-webkit-keyframes fadeOut {
	  0% {opacity: 0;}
	  10% {opacity: 1;}
	  90% {opacity: 1;}
	  100% {opacity: 0;}
	}
	@keyframes fadeOut {
	  0% {opacity: 0;}
	  10% {opacity: 1;}
	  90% {opacity: 1;}
	  100% {opacity: 0;}
	}
	.errors{
	  position: fixed;
	  z-index: 10000;
	  padding: 10px;
	  top: 0px;
	  left: 0px;
	  right: 0px;
	  bottom: 0px;
	  pointer-events: none;
	}
	.alert {
	  animation: fadeOut 2700ms ease-in 0s 1 forwards;
	  -webkit-animation: fadeOut 2700ms ease-in 0s 1 forwards;
	  -moz-animation: fadeOut 2700ms ease-in 0s 1 forwards;
	  width: 250px;
	  float: right;
	  clear: both;
	  margin-bottom: 5px;
	  pointer-events: auto;
	}

## Deployment

#### Deploying denga MupX

Jika anda memilih deploy di server anda sendiri on your own servers, [MupX](https://github.com/arunoda/meteor-up/tree/mupx) adalah handy Docker deploy script yang akan set up dan deploy aplikasi anda ke server Digital Ocean, AWS, dll.

## Templates

Buat file baru dengan nama main.html didalam direktori /client, dan tulis kode seperti dibawah ini :

	<head>
		<title>Microscope</title>
	</head>
	<body>
		<div class="container">
			<header class="navbar navbar-default" role="navigation">
				<div class="navbar-header">
				<a class="navbar-brand" href="/">Microscope</a>
				</div>
			</header>

			<div id="main">
				{{> postsList}}
			</div>
		</div>
	</body>

Ini adalah main app template. Anda lihat kode {{> postsList}} ini adalah **template inclusion tag**, yang mana kita dapat menyisipkan file postsList disini. Template lain adalah seperti yang akan di jelaskan dibawah ini.

### Meteor Templates

* Buat direktori /templates didalam /client . Disini kita akan menaruh semua template, 
* Buat direktori /posts didalam /templates untuk file yang berhubungan dengan post.

> #### Finding Files
+ Meteor sangat baik dalam menemukan file-file. Dimanapun anda menaruh kode didalam direktori / Meteor akan menemukan dan meng-compilenya dengan baik. Artinya anda **tidak perlu** secara manual menuliskan **include paths** untuk file JavaScript atau CSS.
+ Juga berarti anda dapat menaruh seluruh file dalam direktori yang sama atau semua kode di dalam file yang sama. Tapi sejak Meteor akan compile semua menjadi single minified file, maka kita mending menyusun file kita serapih mungkin secara terstruktur.

Buat template kedua didalam client/templates/posts, buat file posts_list.html, seperti sbb :

	<template name="postsList">
	  <div class="posts">
	    {{#each posts}}
	      {{> postItem}}
	    {{/each}}
	  </div>
	</template>

Ini adalah daftar post yang akan ditampilkan dengan kode loop {{#each posts}}	

dan buat juga file didalam client/templates/posts/post_item.html :

	<template name="postItem">
		<div class="post">
			<div class="post-content">
				<h3><a href="{{url}}">{{title}}</a><span>{{domain}}</span></h3>
			</div>
		</div>
	</template>

> **Catatan** : name="postsList" attribute dari **template element**. Ini adalah nama yang akan digunakan oleh Meteor untuk 'keep track' templatenya masing-masing.

### Spacebars

Kami akan mengenalkan kepada anda "Meteor’s templating system", yaitu **Spacebars**, Spacebars adalah kode HTML sederhana, dengan tambahan dari tiga hal yaitu: 

* inclusions (atau dikenal sebagai “partials”), 
* expressions dan 
* block helpers.

Inclusions menggunakan sintaks 

	{{> templateName}}, 

kode ini perintahankan Meteor untuk menggantikan "the inclusion" dengan template yang telah dbuat sebelumnya dengan nama yang sama (dalam kasus ini **postItem** ).

Expressions seperti ini:  

	{{title}} 

kode ini akan memanggil property dari object yang bersangkutan atau *return value* dari 
template helper yang telah di *defined* di *current template’s manager* (akan dipelajari kemudian).

Block helpers 

	{{#each}}
		...
	{{/each}}
	
atau 

	{{#if}}
		...
	{{/if}}

adalah special tags untuk control flow dari template.

**Penjelasan**

Pada postsList template, kita lakukan perulangan (iterating) pada posts object dengan block helper {{#each}}...{{/each}}. Kemudian untuk masing-masing perulangan kita sertakan postItem template.

Kemana posts object ini datangnya? Adalah dari template helper, dan anda boleh berfikir ini sebagai *placeholder* untuk *dynamic value*.

Pada postItem template menggunakan tiga expressions yaitu: {{url}} dan {{title}} keduanya mengembalikan nila 'document’s properties', dan {{domain}} calls "template helper".

### Template Helpers 

Meteor memisahkan antara templates dan logic nya, akan tetapi dalam prosesnya template membutuhkan *helpers*. 

*Helpers* seperti tukang masak mengambil bahan baku mentah (data anda) dan menyiapkannya, sebelum memberikan hidangan jadi (the templates) kepada pelayan sebagai orang yang kemudian menyajikannya kepada anda.

> Dengan kata lain, saat peran template berakhir *the helpers* adalah orang yang melakukan pekerjaan berat dengan menetapkan *value* untuk masing-masing variable.

---

> **Controllers?**
Mungkin anda berfikir file yang berisi template’s helpers seperti semacan controller. Tapi hal yang diragukan sebagai *controllers* (pada MVC), karena memiliki perbedaan fungsi.
Jadi kita tidak akan menggunakan terminology 'controller', secara sederhana sebut saja sebagai “**the template’s helpers**“ atau “**the template’s logic**” jika subyek nya adalah template’s JavaScript kode.

Secara sederhana, kita akan mengadobsi nama yang sama pada file yang memuat helpers pada template, tapi dengan ekstensi **.js**. Sekarang buatlah file posts_list.js didalam 
client/templates/posts.

Mulailah membuat helper Pertama client/templates/posts/posts_list.js:

	var postsData = [
		{
			title: 'Introducing Telescope',
			url: 'http://sachagreif.com/introducing-telescope/'
		},
		{
			title: 'Meteor',
			url: 'http://meteor.com'
		},
		{
			title: 'The Meteor Book',
			url: 'http://themeteorbook.com'
		}
	];

	Template.postsList.helpers({
		posts: postsData
	});

Coba anda buka browser anda http://localhost:3000

![](http://res.cloudinary.com/medioxtra/image/upload/c_scale,w_800/v1481337637/microscope_eobfq6.png)

Kita melakukan 2 hal disini: 

* Pertama kita setting *dummy* data didalam postsData array. Yang biasanya kita buat di database (chapter berikutnya) jadi sementara kita buat static data dulu.

* Kedua kita gunakan **Template.postsList.helpers() function** untuk membuat template
helper memanggil (*called*) **posts** yang akan mengembalikan (returns) **postsData array** yang telah kita buat.

Anda ingat? Kita menggunakan posts helper dalam postsList template:

	<template name="postsList">
		<div class="posts page">
			{{#each posts}}
				{{> postItem}}
			{{/each}}
		</div>
	</template>

### The domain Helper

Sekarang kita membuat post_item.js untuk menempatkan logic postItem template’s 

client/templates/posts/post_item.js

	Template.postItem.helpers({
		domain: function() {
			var a = document.createElement('a');
			a.href = this.url;
			return a.hostname;
		}
	});

Kali ini nilai domain helper’s bukan lagi sebuah array, tapi *anonymous* function. Pattern seperti ini sudah lazim dan *useful* dibandingkan dengan contoh dummy data sebelumnya.

![](http://res.cloudinary.com/medioxtra/image/upload/c_scale,w_800/v1481341744/microscop_u8jyyw.png)

Domain helper ambil URL dan mengembalikan domain nya via "*JavaScript magic*". Tapi bagaimana url tersebut berasal? Jawabnya kita lihat kembali posts_list.html template. Dimana {{#each}} block helper tidak hanya melakukan perulangan (*iterates*) array saja, tapi juga **mengisi nilai**(value) dari "**this**"  ke dalam **block untuk perulangan object**.

Artinya antara kedua {{#each}} tags, masing-masing post ditetapkan (*assigned*) untuk "**this**" berturut-turut, dan sepanjang included template’s manager ( post_item.js ).

We now understand why this.url returns the current post’s URL. And moreover, if we use
{{title}} this.title and {{url}} inside our post_item.html template, Meteor knows that we mean and this.url and returns the correct values.