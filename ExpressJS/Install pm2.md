# Deploy Aplikasi Node.js Menggunakan PM2
[Link resources](https://www.codepolitan.com/tutorial/deploy-aplikasi-nodejs-menggunakan-pm2-57bbfb6931a1d-4)

## Steps

	$ npm install express

Install PM2, globally

	$ npm i -g pm2


Membuat aplikasi Express.js:

cd to/workspace/path:

	$ express myapp

	$ cd myapp

	$ npm install

Membuat aplikasi kedua yang akan menjadi bahan percobaan:

	$ express another_myapp

	$ cd another_myapp
	
	$ npm install

Pada kedua folder proyek tersebut akan muncul sebuah folder bernama node_modules library yang dibutuhkan oleh proyek Express.js. Secara default, Express.js menjalankan aplikasinya di port 3000, sekarang kita harus merubah salah satu proyek tersebut untuk menjalankan aplikasi di port lain. Kita akan mengubah file www yang ada di folder another_myapp/bin. Ubah port-nya menjadi 3030 seperti pada source code berikut:	

	var port = normalizePort(process.env.PORT || '3030');
	app.set('port', port);

Jalankan kedua proyek tersebut di konsol tanpa menggunakan PM2 terlebih dahulu:

	$ cd myapp
	$ npm start

	cd another_myapp
	$ npm start

Kedua aplikasi sudah dapat berjalan dan diakses via web browser:

### Mencoba PM2 terhadap Aplikasi Node.js

Bila sebelumnya kita hanya menjalankannya secara manual untuk masing - masing proyek, sekarang kita akan coba langsung memasangnya di PM2. Bila kita masih menjalankan kedua aplikasi di konsol, silahkan matikan terlebih dahulu. Kemudian mari kita lihat, panduan quickstart apakah yang dapat digunakan untuk memulai penggunaan PM2:

	$ pm2

Seperti yang kita lihat, PM2 memiliki sejumlah perintah yang siap membantu kita sekaligus memberikan contoh penggunaan dasar dengan menggunakan PM2. Sekarang mari kita lihat apakah ada aplikasi yang berjalan diatas PM2 atau tidak:

	$ pm2 list

Ternyata saat ini belum ada satu pun aplikasi yang telah dipasang di PM2. Sekarang kita akan menggunakan perintah start untuk menjalankan myapp dan another_myapp diatas PM2. Berikut adalah perintah untuk menjalankan aplikasi Node.js diatas PM2:

	~/sites_express/sites$ pm2 start myapp/bin/www -i 0 --name "myapp"	

Kemudian jalankan juga another_myapp dengan perintah yang sama namun berbeda nama dan folder:

	~/sites_express/sites$ pm2 start myapp/bin/www -i 0 --name "another_myapp"

Hasilnya, kita dapat melihat another_myapp telah ditambahkan ke dalam PM2. Mengapa file bin/www yang dijalankan? karena Express.js menyimpan objek dan konfigurasi utama server di dalam script tersebut. Bila kita memiliki sebuah script Node.js yang sudah berisi objek server, kita dapat langsung menjalankannya dengan PM2. Berikut adalah beberapa penjelasan dari setiap bagian kolom diatas:

	....	

Monitoring sederhana menggunakan perintah berikut:

	$ pm2 monit

Sebuah tools yang memperlihatkan apakah aplikasi Node.js sedang menangani banyak request atau tidak.	

Untuk melihat monitoring tersebut berjalan atau tidak, kita dapat menggunakan Apache Benchmark untuk menghantam kedua aplikasi tersebut. Coba perhatikan perintah berikut ini:

	$ ab -n 10000 -c 1000 http://localhost:3000/

to be continue later 	









