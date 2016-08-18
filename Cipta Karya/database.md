# Aplikasi Database Cipta Karya

![image dbcp](http://res.cloudinary.com/medioxtra/image/upload/v1471147323/database-development_vrifoz.png)

Aplikasi Database Cipta Karya adalah sistem penyimpanan data Direktorat Jendral Cipta Karya Kementrian Pekerjaan Umum dan Perumahan Rakyat, yang bersumber dari data .... 

Aplikasi ini dibuat untuk membantu proses pencarian data (semua data dibawah naungan DJ Cipta Karya) menuju One Data dalam rangka upaya peningkatan kinerja .... 

## Manfaat

Manfaat dari Aplikasi Database Cipta Karya Madalah sebagai berikut.

* Mempermudah membaca data-data .. 
* Mempermudah melakukan analisis ..
* Mempermudah membuat grafik hasil pencarian data ..
* Dapat merubah hasil pencarian data dalam bentuk file excel (.xls) agar dapat diolah sesuai kebutuhan
* Dapat mencetak langsung hasil pencari

## Kelebihan

Kelebihan dari Aplikasi Database Cipta Karya adalah :

* Dapat mencari data dari tingkat provinsi hingga kelurahan dengan menggunakan banyak  indikator-indikator...
* Dapat menyajikan data berupa grafik dan bentuk print data berdasarkan pencarian data.
* Data dapat di export ke dalam bentuk data excel sehingga hasil data pencarian dapat di olah untuk kebutuhan tertentu.
* Dapat membandingkan tingkat perkabupaten hingga perkelurahan dalam bentuk grafik.
* Data grafik dapat di print dan di save as untuk kebutuhan data yang diperlukan.
* Dapat mengetahui secara rinci data ... 
* Berbasis web sehingga aplikasi tidak harus di install kedalam setiap komputer cukup kedalam 1 komputer server sehingga komputer yang tersambung dalam jaringan bisa menggunakan aplikasi ini.

# Latar Belakang dan Referensi

## Cara Membangun Sebuah Database yang Baik

Sebelum kita mengetahui bagaimana cara membuat database yang baik,alangkah lebih baiknya jika kita mengetahui dulu apa itu database.

**DATABASE** adalah suatu tempat kumpulan dari data yang tersimpan dan diatur serta diorganisasikan sedemikian hingga hingga data tersebut dapat diambil atau dicari dengan mudah dan efisien. Atau bisa diartikan juga sebagai kumpulan data yang saling berhubungan yang disimpan dalam suatu tempat tertentu.

Untuk membuat sebuah sistim database dibutuhkan suatu aplikasi perangkat lunak (*software application*) sebagai alat memanipulasi dan penyajian data, yaitu Membuat (*Create*), Membaca (*Read*), Mengubah (*Update*) dan Menghapus (*Delete*) data-data tersebut. 

Memanipulasi dan memperoleh data/informasi dengan praktis dan efisien kita sebut dengan istilah DataBase Management System (DBMS). 

Saat ini DBMS yang cukup popular saat ini digunakan antara lain adalah :

* MYSQL database
* ORACLE database 
* MsSQL database
* PostgreSQL database dll.

# Pengertian Basis Data

<center>![what is](http://res.cloudinary.com/medioxtra/image/upload/v1471148507/db_u3p0vt.jpg)</center>

**Basis Data**

Basis data (database) adalah suatu kumpulan data yang disusun dalam bentuk tabel-tabel yang saling berkaitan maupun berdiri sendiri dan disimpan secara bersama-sama pada suatu media. Basis data dapat digunakan oleh satu atau lebih program aplikasi secara optimal, data disimpan tanpa mengalami ketergantungan pada program yang akan menggunakannya.

Terdapat beberapa aturan yang harus dipatuhi pada file basis data agar dapat memenuhi kriteria sebagai suatu basis data, yaitu:

1. Kerangkapan data, yaitu munculnya data-data yang sama secara berulang-ulang pada file basis data.
2. Inkonsistensi data, yaitu munculnya data yang tidak konsisten pada field yang sama untuk beberapa file dengan kunci yang sama. 
3. Data terisolasi, disebabkan oleh pemakaian beberapa file basis data. Program aplikasi tidak dapat mengakses file tertentu dalam sistem basis data tersebut, kecuali program aplikasi dirubah atau ditambah sehingga seolah-olah ada file yang terpisah atau terisolasi terhadap file yang lain. 
4. Keamanan data, berhubungan dengan masalah keamanan data dalam sistem basis data. Pada prinsipnya file basis data hanya boleh digunakan oleh pemakai tertentu yang mempunya wewenang untuk mengakses. 
5. Integrasi data, berhubungan dengan unjuk kerja sistem agar dapat melakukan kendali atau kontrol pada semua bagian sistem sehingga sistem selalu beroperasi dalam pengendalian penuh.

## Bagian-Bagian Basis Data

Membangun basis data adalah langkah awal dari pembuatan sebuah aplikasi. Keberhasilan dalam membangun basis data akan menyebabkan program lebih mudah dibaca, mudah dikembangkan dan mudah mengikuti perkembangan perangkat lunak. Berikut ini diuraikan mengenai komponen-komponen yang terdapat dalam basis data.

1. Tabel
Tabel adalah kumpulan dari suatu field dan record. Dalam hal ini biasanya field ditunjukan dalam bentuk kolom dan record ditunjukan dalam bentuk baris.

2. Field
Field adalah sebutan untuk mewakili suatu record. Misalnya seorang pegawai dapat dilihat datanya melalui field yang diberikan padanya seperti nip, nama, alamat, dan lain-lain.

3. Record
Record adalah kumpulan elemen-elemen yang saling berkaitan menginformasikan tentang suatu isi data secara lengkap. Satu record mewakili satu data atau informasi tentang seseorang misalnya, nomor daftar, nama pendaftar, alamat, tanggal masuk.

4. Primary Key
Primary key adalah suatu kolom (field) yang menjadi titik acuan pada sebuah tabel, bersifat unik dalam artian tidak ada satu nilai pun yang sama atau kembar dalam tabel tersebut, dan dalam satu tabel hanya boleh ada satu primary key.

5. Foreign Key
Foreign key atau disebut juga **kunci relasi** adalah suatu kolom dalam tabel yang digunakan sebagai **“kaitan”** untuk melengkapi satu hubungan yang didapati dari tabel induk, dan biasanya hubungan yang terjalin antar tabel adalah satu ke banyak (one to many).

6. Index
Index adalah struktur basis data secara fisik, yang digunakan untuk optimalisasi pemrosesan data dan mempercepat proses pencarian data.

## Relasi (relationship) Basis Data

Basis data adalah kumpulan file yang saling berkaitan. Pada model data relasional hubungan antar file direlasikan dengan kunci relasi (relation key), yang merupakan kunci utama dari masing- masing file.
Perancangan basis data yang tepat akan menyebabkan paket program relasional akan bekerja secara optimal.

Relasi antara dua file atau dua tabel dapat dikategorikan menjadi tiga macam. Demikian pula untuk membantu gambaran relasi secara lengkap terdapat juga tiga macam relasi dalam hubungan atribute dalam satu file.

### 1. One to one relationship 
<center>![one to one](http://res.cloudinary.com/medioxtra/image/upload/v1471149720/one_to_one_relasi_lbqwuk.jpg)</center>

<center>Model relasi one to one relationship</center>

Hubungan antara file pertama dengan file kedua adalah satu berbanding satu. Hubungan tersebut dapat digambarkan dengan **tanda kotak untuk menunjukan table** dan relasi antara keduanya diwakilkan dengan **tanda panah tunggal**.

### 2. One to many relationship
<center>![one to many](http://res.cloudinary.com/medioxtra/image/upload/v1471150354/relasi_one_to_many_hirtin.jpg)</center>

<center>Model relasi one to many relationship</center>

Hubungan antara file pertama dengan file kedua adalah satu berbanding banyak atau dapat pula dibalik banyak lawan satu. Hubungan tersebut dapat digambarkan dengan tanda kotak untuk menunjukkan tabel dan relasi antara keduanya diwakilkan dengan **tanda panah ganda** pada salah satu hubungan.

### 3. Many to many relationship

<center>![many to many](http://res.cloudinary.com/medioxtra/image/upload/v1471150705/relasi_many_to_many_yftpna.jpg)</center>
 
<center>Model relasi many to many relationship</center>

Hubungan antara file pertama dengan file kedua adalah banyak berbanding banyak. Hubungan tersebut dapat digambarkan dengan tanda kotak untuk menunjukkan tabel dan relasi antara keduanya diwakilkan dengan tanda panah ganda pada kedua hubungan tersebut.

---

### Dalam melakukan proses desain database yang baik harus melelui beberapa langkah, yaitu:

* Analisis Persyaratan : Memahami dan mengetahui data yang harus disimpan dalam database, aplikasi apa yang harus dibangun di atasnya, jenis operasi apa yang akan digunakan.

* Desain Data Base Konseptual : Berdasarkan informasi yang diperoleh dari tahap analisis persyaratan inilah dipergunakan untuk mengembangkan deskripsi data menjadi lebih tinggi. Pada langkah ini desainer sering membuat yang namanya model E-R yang tujuan untuk membuat penyederhanaan gambaran tentang data yang sesuai dengan pemikiran user / pengguna.

* Desain Data Base Logika : disinilah proses merubah model E-R skema database yang rasional. Dengan tujuan untuk mendapatkan skema konseptual pada data rasional sehingga sering disebut skema logika.

* Perbaikan Skema : pengecekan sekumpulan relasi dalam skema sebelumnya (skema database rasional), supaya dapat menemukan problem yang ada dan memperbaikinya.

* Desain Data Base Fisik : pembentukan indeks pada beberapa tabel yang telah dibuatlah pada tahap ini dikerjakan. mengelompokkan tabel atau mendesain ulang yang bersifat substansial terhadap bagian dari skema database.

* Desain Aplikasi dan Keamanan : Keseluruhan proyek software yang menggunakan DBMS sebaiknya memperhitungkan faktor-faktor aplikasi yang ada diluar database, seperti enkripsi, digital sinature, dll.

## Langkah-Langkah Terpenting Dalam Pembuatan Database Yang Sistematis

### 1. Analisis Persyaratan: 

Langkah pertama dalam mendesain sebuah aplikasi database adalah memahami dan mengetahui data yang harus disimpan di dalam database, aplikasi apa yang harus dibangun diatasnya, dan jenis operasi apa yang lebih banyak digunakan, dan subjek untuk melakukan persyaratan yang ada. Dengan kata lain, kita harus tahu apa yang diinginkan pengguna database tersebut. Biasanya ini adalah sebuah proses informal yang melibatkan partisipasi kelompok pengguna, studi tentang lingkungan pegoperasian saat ini dan bagaimana perkiraan perubahan lingkungan tersebut, analisis dokumen yang ada dalam suatu aplikasi yang diharapkan akan diganti atau dilengkapi oleh database, dan seterusnya. Banyak metodologi yang diusulkan untuk menyusun dan menampilkan informasi yang dikumpulkan pada langkah tersebut. Beberapa alat otomatis pun telah dikembangkan untuk mendukung proses ini.

### 2. Desain Database Konseptual: 

Informasi dikumpulkan pada saat analisis persyaratan digunakan untuk mengembangkan deskripsi data tingkat tinggi yang harus disimpan dalam database, bersama dengan batasan yang telah diketahui untuk menetapkan penyimpanan data tersebut. Langkah ini sering dilakukan dengan menggunkan model ER. Model ER adalah salah satu dari model data tingkat tinggi, atau semantik, yang digunakan dalam desain database. Tujuannya adalah menciptakan gambaran sederhana tentang data yang mirip dengan pemikiran pengguna dan pengembang mengenai data tersebut (orang dan proses yang dinyatakan dalam data tersebut). Hal tersebut menfasilitasi diskusi di antara orang-orang yang terlibat dalam proses desain, bahkan mereka yang tidak mempunyai latar belakang teknis. Pada saat yang sama, desain awal harus akurat untuk membantu ketepatan translasi ke dalam sebuah model data yang didukung oleh sistem database komersial (yang dalam prakteknya berarti model relasional).

### 3. Desain Database Logika:

 Kita harus memilih sebuah DBMS untuk mengimplementasikan desain database kita, dan mengubah konsep desain database menjadi sebuah skema database dalam model data dari DBMS terpilih. Kita hanya akan memperhatikan DBMS relasional, dan dengan demikian tugas desain logika adalah mengubah skema ER menjadi skema database relasional.

### 4. Perbaikan Skema:

 Langkah keempat dalam desain database adalah analisis sekumpulan relasi dalam skema database relasional untuk mengidentifikasi permasalahan yang muncul, dan memperbaikinya. Berbeda dengan analisis persyaratan dan langkah-langkah desain konseptual, yang secara esensial bersifat subjektif, perbaikan skema dapat dipandu oleh beberapa teori yang kuat dan bagus.  Langkah keempat ini, para akademis IT lebih sering disebut dengan Normalisasi.

### 5. Desain Database Fisik: 

Langkah ini, kita juga mempertimbagkan beban kerja umum yang diharapkan dapat didukung oleh database kita dan memperbaiki desain database di masa mendatang untuk memastikan terpenuhinya kriteria performa yang diinginkan. Langkah ini hanya mencakup pembuatan indeks pada beberapa tabel dan mengelompokkan beberapa tabel, atau bahkan melibatkan desain ulang yang substansial terhadap beberapa bagian skema database yang didapat dari langkah pertama desain database.

### 6. Desain Aplikasi dan Keamanan: 

Semua proyek perangkat lunak yang melibatkan sebuah DBMS harus mempertimbangkan aspek aplikasi yang berada di luar database itu sendiri. Metodologi desain seperti UML mencoba menekankan desain perangkat lunak dan siklus pengembangan yang lengkap. Secara singkat, kita harus bisa mengidentifikasi entitas (contohnya pengguna, grup-grup pengguna, dan bagian-bagian lain) dan proses-proses yang terlibat dalam aplikasi. Kita harus menggambarkan peran setiap entitas dalam setiap proses yang akan direfleksikan pada beberapa tugas aplikasi, sebagai bagian dari aliran 
kerja lengkap untuk tugas tersebut. Untuk tiap peran, kita harus bisa mengidentifikasi bagian database yang harus bisa diakses dan yang tidak bisa diakses, dan kitah harus bisa menganmbil langkah untuk memastikan bahwa aturan akses terseut dilakukan. DBMS memberikan beberapa mekanisme untuk membantu langkah tersebut.

# Entity-Relationship

## Model Entity-Relationship (ER)

Model **Entity-Relationship** (ER) adalah **model data konseptual tingkat tinggi** untuk perancangan basis data. Model data konseptual adalah **himpunan konsep yang mendeskripsikan struktur basis data, transaksi pengambilan dan pembaruan basis data**. 

Model ER adalah data konseptual tak tergantung DBMS dan platform perangkat keras tertentu. Model ER dikemukakan oleh Chen [1976]. Sejak itu, telah memperoleh banyak perhatian dan perluasan. 

Model ER adalah persepsi terhadap dunia nyata sebagai terdiri objek-objek dasar yang disebut **entitas** dan keterhubungan (relationship) antar entitas-entitas itu. 

Konsep paling dasar di model ER adalah **entitas**, **relationship** dan **atribut**.

### Komponen-komponen utama model ER adalah :

1. Entitas (entity), Entitas memodelkan objek-objek yang berada diperusahaan/lingkungan.

2. Relationship. Relationship memodelkan koneksi/hubungan di antara entitas-entitas.

3. Atribut-atribut (properti-properti), memodelkan properti-properti dari entitas dan relationship.

4. Konstrain-konstrain (batasan-batasan) integritas, konstrain-konstrain ketentuan validitas.

### Entitas (Entity) dan Himpunan Entitas (Entitas Sets)

**Entitas merupakan individu yang mewakili sesuatu yang nyata (eksistensinya) dan dapat dibedakan dari sesuatu yang lain**. Sebuah kursi yang kita duduki, seseorang yang menjadi pegawai di sebuah perusahaan dan sebuah mobil yang melintas di depan kita adalah entitas.

Sekelompok entitas yang sejenis dan berada dalam lingkup yang sama membentuk sebuah himpunan entitas (*entity sets*). Sederhananya, entitas menunjuk pada individu suatu objek, sedang himpunan entitas menunjuk pada rumpun (*family*) dari individu tersebut. 

Seorang pasien, misalnya akan dimasukkan dalam himpunan entitas pasien. Sedang seorang dokter akan ditempatkan dalam himpunan entitas dokter. 

Dalam berbagai pembahasan/literature, penyebutan **himpunan entitas** (kurang praktis) ini seringkali digantikan dengan sebutan entitas saja. 

Karena itu sering ditemui, penggunaan istilah entitas (entity) di sebuah literature sebenarnya menunjuk pada himpunan entitas.

### Kunci Entitas

Sebagaimana model relasional, adalah penting dan berguna untuk memasukkan kunci yang diasosiasikan dengan himpunan entitas. Kunci pada himpunan entitas S, adalah himpunan atribut A. Sehingga tidak ada dua entitas di S yang mempunyai nilai sama untuk tiap atribut di A dan tidak ada subset di A yang dapat menjadi kunci di S, dengan demikian kunci mempunyai property minimal.

### Atribut (Atributes/Properties)

Setiap entitas pasti memiliki atribut yang mendeskripsikan karakteristik (property) dari entitas tersebut. 

Penentuan / pemilihan atribut-atribut yang relevan bagi sebuah entitas merupakan hal penting lainnya dalam pembentukan model ER. Contoh : nim, nama, alamat, kode.

### Relasi (Relationship) dan Himpunan Relasi (Relationship Sets)

Relasi menunjukkan adanya hubungan di antara sejumlah entitas yang berasal dari himpunan entitas yang berbeda. 

Misalnya, entitas seorang mahasiwa dengan 

	nim = 980001 dan 
	nama_mhs = Ali Akbar (yang ada di himpunan entitas Mahasiswa) 

mempunyai relasi dengan entitas sebuah mata kuliah dengan 

	kode_kul=IF-110 dan 
	nama_kul=Struktur Data. 

Relasi diantara kedua entitas tadi mengandung arti bahwa mahasiswa tersebut sedang mengambil/mempelajari mata kuliah tersebut di sebuah perguruan tinggi yang ditinjau.

Kumpulan semua relasi diantara entitas-entitas yang terdapat pada himpunan entitas-himpuan entitas tersebut membentuk himpunan relasi (relationship sets). 

Sebagaimana istilah himpunan entitas yang banyak sekali disingkat menjadi entitas, istilah himpunan relasi jarang sekali digunakan dan lebih sering disingkat dengan istilah relasi saja.

### Kardinalitas/derajat Relasi

Kardinalitas Relasi adalah **menunjukkan jumlah maksimum entitas yang dapat berelasi dengan entitas pada himpunan entitas yang lain**. Kardinalitas relasi merujuk kepada hubungan maksimum yang terjadi dari himpunan entitas yang satu ke himpunan entitas yang lain dan begitu juga sebaliknya. 

Kardinalitas di antara dua himpunan entitas (misalnya A dan B) dapat berupa :

1. Satu ke satu (One to One)
setiap entitas pada himpunan entitas A berhubungan dengan paling banyak dengan satu entitas pada himpunan entitas B, 
begitu juga sebaliknya setiap entitas pada himpunan entitas B berhubungan dengan paling banyak dengan satu entitas pada himpunan entitas A.

2. Satu ke Banyak (one to many)
setiap entitas pada himpunan entitas A dapat berhubungan dengan banyak entitas pada himpunan entitas B, 
tetapi tidak sebaliknya, dimana setiap entitas pada himpunan entitas B berhubungan dengan paling banyak dengan satu entitas pada himpunan entitas A.

3. Banyak ke Satu (Many to One),
setiap entitas pada himpunan entitas A berhubungan dengan paling banyak dengan satu entitas pada himpunan entitas B, 
tetapi tidak sebaliknya, dimana setiap entitas pada himpunan entitas A berhubungan dengan paling banyak satu entitas pada himpunan entitas B.

4. Banyak ke Banyak (Many to Many)
setiap entitas pada himpunan entitas A dapat berhubungan dengan banyak entitas pada himpunan entitas B, 
demikian juga sebaliknya, di mana setiap entitas pada himpunan entitas B dapat berhubungan dengan banyak entitas pada himpunan entitas A.

## Diagram Entity-Relationship (ER)

Penggambaran Model ER secara sistematis dilakukan melalui diagram ER. Notasi-notasi simbolik di dalam Diagram ER yang dapat digunakan adalah:

1. Persegi panjang, menyatakan **Himpunan Entitas**.

2. Lingkaran/Elips, menyatakan **atribut** (Atribut yang berfungsi sebagai key digaris bawahi).

3. Belah ketupat, menyatakan **Himpunan Relasi**.

4. Garis, sebagai **penghubung** antara Himpunan Relasi dengan Himpunan Entitas dan Himpunan Entitas dengan Atributnya.

5. Kardinalitas Relasi dapat dinyatakan dengan banyaknya garis cabang atau dengan pemakaian angka (1 dan 1 untuk relasi one to one, 1 dan N untuk relasi one to many atau N dan N untuk relasi many to many).

## Tahap Pembuatan Diagram ER

Diagram ER selalu dibuat secara bertahap. Paling tidak ada dua kelompok penahapan yang biasa ditempuh di dalam pembuatan diagram ER, yaitu :

### Tahap pembuatan Diagram ER awal (preliminary design). Yaitu :

* Melakukan pengidentifikasian dan menetapkan seluruh himpunan entitas yang akan terlibat. 
* Menentukan atribut-atribut key dari masing-masing himpunan entitas. 
* Mengidentifikasi dan menetapkan seluruh himpunan relasi di antara himpunan entitas-himpunan entitas yang ada beserta foreign key nya. 
* Menentukan derajat/kardinalitas relasi untuk setiap himpunan relasi. 
* Melengkapi himpunan entitas dan himpunan relasi dengan atribut-atribut deskriptif (non key).

### Tahap optimasi Diagram ER (final design).



