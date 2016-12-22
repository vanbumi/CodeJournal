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

Kita sekarang paham this.url mengembalikan current post’s URL, jika kita menggunakan {{title}} this.title dan {{url}} didalam post_item.html template, Meteor tahu this.url akan mengembalikan values yang benar.

### JavaScript Magic

Penjelasan dari kode ini:

	Template.postItem.helpers({
		domain: function() {
			var a = document.createElement('a');
			a.href = this.url;
			return a.hostname;
		}
	});

* Pertama kita membuat *empty anchor* ( a ) HTML element dan menyimpannya ke dalam memory, 
* Kemudian kita set href attribute equal dengan the current post’s URL.
* Terakhir kita mengembalikan element a dengan spesial hostname property untuk mengambil link dari nama domain tersebut tanpa URL sisannya. (*Finally, we take advantage of that a element’s special hostname property to get back the link’s domain name without the rest of the URL*).

*** Hot Code Reload

You might have noticed that you didn’t even need to manually reload your browser
window whenever you changed a file.
This is because Meteor tracks all the files within your project directory, and automatically
refreshes your browser for you whenever it detects a modification to one of them.
Meteor’s hot code reload is pretty smart, even preserving the state of your app in-between
two refreshes!

---

## Collections

A collection is a special data structure that takes care of storing your data in the permanent, server-side MongoDB database, and then synchronising it with each connected user’s browser in real-time.

We want our posts to be permanent and shared between users, so we’ll start by creating a
collection called Posts to store them in.

Collections are pretty central to any app, so to make sure they are always defined first we’ll put them inside the lib directory. So if you haven’t done so already, create a collections/ folder inside lib , and then a posts.js file inside it. Then add:

	Posts = new Mongo.Collection('posts');

Menggunaka Var (variable) atau tidak usah?

In Meteor, the var keyword limits the scope of an object to the current file. Here, we
want to make the Posts collection available to our whole app, which is why we’re not
using the var keyword.

### Storing Data

Three basic ways of storing data at their disposal, each filling a different role:

* **The browser’s memory**: things like JavaScript variables are stored in the browser’s
memory, which means they’re not permanent: they’re local to the current browser tab, and
will disappear as soon as you close it.

* **The browser’s storage**: browsers can also store data more permanently using cookies or
Local Storage. Although this data will persist from session to session, it’s local to the current user (but available across tabs) and can’t be easily shared with other users.

* **The server-side database**: the best place for permanent data that you also want to make
available to more than one user is in a good old database (MongoDB being the default
solution for Meteor apps).

Meteor makes use of all three, and will sometimes synchronize data from one place to another (as we’ll soon see).

### Client & Server

Code inside folders that are not **client**/ or **server**/ will run in both contexts. So the **Posts collection** is available to both client and server. However, what the collection does in each environment can be pretty different.

On the server, the collection has the job of talking to the MongoDB database, and reading and
writing any changes. In this sense, it can be compared to a standard database library.

On the client however, the collection is a copy of a subset (bagian) of the real, canonical collection. The client-side collection is constantly and (mostly) transparently kept up to date with that subset in real-time.

### Console vs Console vs Console

Di meteor kita akan mengenal beberapa jenis console:

* Terminal

* Browser Console

* Meteor Shell
Called from the Terminal with 'meteor shell'

* Mongo Shell
Called from the Terminal with 'meteor mongo'

### Server-Side Collections

Get help

	db.help()

	DB methods:
		db.adminCommand(nameOrDocument) - switches to 'admin' db, and runs command [ just calls db.runCommand(...) ]
		db.auth(username, password)
		db.cloneDatabase(fromhost)
		db.commandHelp(name) returns the help for the command
		db.copyDatabase(fromdb, todb, fromhost)
		db.createCollection(name, { size : ..., capped : ..., max : ... } )
		db.createUser(userDocument)
		db.currentOp() displays currently executing operations in the db
		db.dropDatabase()
		db.eval() - deprecated
		db.fsyncLock() flush data to disk and lock server for backups
		db.fsyncUnlock() unlocks server following a db.fsyncLock()
		db.getCollection(cname) same as db['cname'] or db.cname
		db.getCollectionInfos([filter]) - returns a list that contains the names and options of the db's collections
		db.getCollectionNames()
		db.getLastError() - just returns the err msg string
		db.getLastErrorObj() - return full status object
		db.getLogComponents()
		db.getMongo() get the server connection object
		db.getMongo().setSlaveOk() allow queries on a replication slave server
		db.getName()
		db.getPrevError()
		db.getProfilingLevel() - deprecated
		db.getProfilingStatus() - returns if profiling is on and slow threshold
		db.getReplicationInfo()
		db.getSiblingDB(name) get the db at the same server as this one
		db.getWriteConcern() - returns the write concern used for any operations on this db, inherited from server object if set
		db.hostInfo() get details about the server's host
		db.isMaster() check replica primary status
		db.killOp(opid) kills the current operation in the db
		db.listCommands() lists all the db commands
		db.loadServerScripts() loads all the scripts in db.system.js
		db.logout()
		db.printCollectionStats()
		db.printReplicationInfo()
		db.printShardingStatus()
		db.printSlaveReplicationInfo()
		db.dropUser(username)
		db.repairDatabase()
		db.resetError()
		db.runCommand(cmdObj) run a database command.  if cmdObj is a string, turns it into { cmdObj : 1 }
		db.serverStatus()
		db.setLogLevel(level,<component>)
		db.setProfilingLevel(level,<slowms>) 0=off 1=slow 2=all
		db.setWriteConcern( <write concern doc> ) - sets the write concern for writes to the db
		db.unsetWriteConcern( <write concern doc> ) - unsets the write concern for writes to the db
		db.setVerboseShell(flag) display extra information in shell output
		db.shutdownServer()
		db.stats()
		db.version() current version of the server

**Mongo shell**

	$ meteor mongo

	> db.posts.insert({title: "A new post"});
	WriteResult({ "nInserted" : 1 })
	
	> db.posts.find();
	{ "_id" : ObjectId("5854ae0dcac95c2a6c2bfbef"), "title" : "A new post" }

### Client-Side Collections

> **Collections client-side!**. When you declare Posts = new Mongo.Collection('posts'); on the client, what you are creating is a local, in-browser cache of the real Mongo collection. When we talk about a client-side collection being a “cache”, we mean it in the sense that it contains a subset of your data, and offers very quick access to this data.

It’s important to understand these points as it’s **fundamental** to the way Meteor works. In general, a client side collection consists (teridiri) of a subset (bagian) of all the documents stored in the Mongo collection (after all, we generally don’t want to send our whole database to the client).

**Secondly**, those documents are stored in **browser memory**, which means that accessing them is basically instantaneous (segera). So there are no slow trips to the server or the database to fetch the data when you call Posts.find() on the client, as the data is already pre-loaded.

### Client-Server Communication

Rather than explaining this in detail, let’s just watch what happens.

Run server:

	myapp$ meteor

Open localhost:3000 with two browser windows, and accessing the browser console in each one. Then, open up the Mongo shell on the command line.

Open new command line, run mongo shell

	myapp$ meteor mongo

On mongo shell (terminal): 

	> db.posts.find();
	{ "_id" : ObjectId("5854ae0dcac95c2a6c2bfbef"), "title" : "A new post" }

On first browser console:

	> Post.findOne();
	Object {_id: M…D.ObjectID, title: "A new post"}

Let’s create a new post. In one of the browser windows, run an insert command:

	› Posts.find().count();
	1
	› Posts.insert({title: "A second post"});
	'xxx'
	› Posts.find().count();
	2

Unsurprisingly, the post made it into the local collection. Now let’s check Mongo:

	› db.posts.find();
	{title: "A new post", _id: ObjectId("..")};
	{title: "A second post", _id: 'yyy'};

s you can see, the post made it all the way back to the Mongo database, without us writing a
single line of code to hook our client up to the server (well, strictly speaking, we did write a single
line of code: new Mongo.Collection('posts') ). But that’s not all!

Bring up the second browser window and enter this in the browser console:

	› Posts.find().count();
	2

The post is there too! Even though we never refreshed or even interacted with the second browser, and we certainly didn’t write any code to push updates out. It all happened magically – and instantly too, although this will become more obvious later.

What happened is that our server-side collection was informed by a client collection of a new post, and took on the task of distributing that post into the Mongo database and back out to all the other connected post collections.

Fetching posts on the browser console isn’t that useful. We will soon learn how to wire this data into our templates, and in the process turn our simple HTML prototype into a functioning realtime web application.

### Populating the Database

What we’d really like to do is display the data, and the changes to that data, on the screen. **To turn our app from a simple web page displaying static data, to a real-time web application with dynamic, changing data**.

First, let’s make sure there’s nothing in the database. We’ll use **meteor reset** , which erases your database and resets your project. You’ll be very careful with this command once
you start working on real-world projects.

Stop the Meteor server (by pressing ctrl-c ) and then, on the command line, run:

	meteor reset

The reset command completely clears out the Mongo database. It’s a useful command in
development, where there’s a strong possibility of our database falling into an inconsistent state.

Let’s start our Meteor app again:

	meteor

### Dynamic Data

If we open up a browser console, we’ll see all three posts loaded up into MiniMongo:	

	› Posts.find().fetch();
	Object, Object, Object

To get these posts into rendered HTML, we’ll use our friend the template helper.	