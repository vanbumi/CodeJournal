# How to Deploy a Node.js App to Heroku

Ref:

* https://scotch.io/tutorials/how-to-deploy-a-node-js-app-to-heroku


## Langkah deploy

Install helmet

	npm i helmet
	
Install compression

	npm i compression
	
Buat folder baru "startup" > file baru "prod.js", yang akan kita gunakan untuk tempat middleware production semua disini, update file prod.js:

	const helmet = require('helmet');
	const compression = require('compression');
	
	module.exports = function(app) {
		app.use(helment());
		app.use(compression());
	}

Kemudian tambahkan require pada file app.js sbb:

	require('./startup/prod')(app);

Gunakan Terminal untuk login heroku:

	heroku login
	
Masih pada Terminal run perintah sbb:

	npm start
	
hasilnya:

	npm ERR! missing script: start

	npm ERR! A complete log of this run can be found in:
	npm ERR!     /Users/dyo-medio/.npm/_logs/2019-02-07T05_37_57_711Z-debug.log
	
untuk itu kita harus update file "package.json" pada "scripts" sbb:

	"scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
		"start": "node app.js"
	},
	
Kemudian coba lagi ```npm start```	
	
Masih pada file package.json tambahkan :

	"engines": {
		"node": "8.6.0"
	}

dapatkan node version gunakan: ```node -v``` pada Terminal.

Tambahkan file ".gitignore" pada root, tambahkan pada ignore sbb:

	node_modules/
	coverage/
	
setelah itu anda save.

Lakukan git command:

	git add .
	git commit -m "ready to deploy"

### Ready to deploy

Pada Terminal run:

	heroku create
	
Cek remote repository di heroku:

	git remote -v
	
Deploy!

	git push heroku master
	
Copy url address nya dan paste ke POSTMAN

	remote:        Released v3
	---> remote:        https://whispering-woodland-70240.herokuapp.com/ deployed to Heroku
	remote: 
	remote: Verifying deploy... done.
	To https://git.heroku.com/whispering-woodland-70240.git
	 * [new branch]      master -> master

Paste pada GET di Postman anda akan menemukan error :

	503 Service Unavailable

Kembali ke Terminal dan lakukan logs

	heroku logs
	
anda bisa lihat error nya dimana dengan membaca logs.

Untuk membuka dengan local browser gunakan perintah:

	heroku local web

Anda bisa juga lihat logs dengan login ke heroku.com > buka aplikasi yang baru dibuat pada pojok kanan atas klik menu > klik View logs.

contoh logs:

	2019-02-07T06:55:45.861284+00:00 app[web.1]: npm ERR! missing script: start
	2019-02-07T06:55:45.875563+00:00 app[web.1]: 
	2019-02-07T06:55:45.876075+00:00 app[web.1]: npm ERR! A complete log of this run can be found in:
	2019-02-07T06:55:45.876315+00:00 app[web.1]: npm ERR!     /app/.npm/_logs/2019-02-07T06_55_45_864Z-debug.log
	2019-02-07T07:40:10.946214+00:00 heroku[web.1]: Starting process with command `npm start`
	2019-02-07T07:40:14.828654+00:00 app[web.1]: npm ERR! missing script: start
	2019-02-07T07:40:14.838280+00:00 app[web.1]: 
	2019-02-07T07:40:14.838549+00:00 app[web.1]: npm ERR! A complete log of this run can be found in:
	2019-02-07T07:40:14.838626+00:00 app[web.1]: npm ERR!     /app/.npm/_logs/2019-02-07T07_40_14_830Z-debug.log
	2019-02-07T09:07:37.580119+00:00 heroku[web.1]: Process exited with status 1


Anda bisa membuka console dari heroku.com, pada pojok kanan atas yang sama menu "more" > open console.

### Set environment variable:

set Node environment to production, pada Terminal gunakan perintah ini:

	heroku config:set NODE_ENV=production
	
run cek env:

	heroku config
	
kemudian ganti listen PORT server seperti dibawah ini:

Sebelumnya:

	// Setup server
	var port = 3000;
	app.listen(port, function () {
		console.log("Server running on port " + port);
	});
	
Menjadi:	

	// PORT
	const port = process.env.PORT || 3000;
	app.listen(port, () => console.log(`Listeining on port ${port}...`));


Jangan lupa setiap melakukan perubahan pada code, anda git commit dan push kembali ke heroku:

	git status
	git add .
	git commit -m "..."
	git push heroku master
	
	
### Setup mongodb pada heroku

Pada dashboard heroku klik menu Resources > Find more add-ons > sidebar menu "Data Stores" > pilih "mlab'.

Buka mlab.com dan login > create new > amazon > sandbox > US California > masukan nama database > continue > submit order > klik database yang baru saja kita buat > klik user > add database user isi data user dan password > create > pada bagian atas anda lihat link connection MongoDB URI copy link tsb.




