# Ringkasan Materi Ruby Training (R-Training)
https://launchschool.com/books/ruby

## Introduction Ruby

Ruby saat itu di ciptakan oleh Yukihiro Matsumoto, atau "Matz", di Jepang pada pertengahan 1990. Dengan tujuan adalah untuk produktivitas dan fun untuk para programer. Dengan menekankan kebutuhan akan software yang mudah di mengerti oleh manusia terlebih dahulu baru kemudian komputer. 

Hingga saat ini perkembangan Ruby terus berlanjut dan semakin populer sebagai bahasa untuk mengembangkan web aplikasi. Sedangkan Ruby on Rails adalah Framework yang dibangun dengan bahasa Ruby oleh David Heinemeier Hansson (DHH), diperkenalkan oleh banyak orang untuk melakukan pemrograman yang menyenangkan.

Ruby memiliki komunitas yang sangat bersemangat dan dinamis untuk mendukung programer pemula dan yang antusias tentang memproduksi kode program yang berkualitas tinggi.

## Tujuan Training

Training ini di tujukan untuk yang belum berpengalaman atau programer pemula, apabila anda menerapkan prinsip dan teknik dalam R-Training ini, anda akan memilki pengetahuan dasar yang cukup untuk melakukan pemerograman dengan Ruby. Anda dapat menggunakan pengetahuan yang didapat di R-Training untuk terus belajar lebih dalam konsep tingkat lanjut. 

R-Training akan membimbing anda pada kebingungan dan mempersingkat waktu belajar bagi pemula, dan juga akan memberikan latihan untuk menerapkan sintak dasar Ruby pada tahap selanjutnya anda akan fokus dalam memberikan solusi pada dunia nyata dan membangun aplikasi yang mumpuni pada dunia nyata.

## Install Ruby

Para peserta R-Training diasumsikan menggunakan Linux machine (Ubuntu 14.04).

Metode dalam menginstal Ruby:

+ rvm
+ rbenv
+ Homebrew (Mac only)
+ Build from source

## Code Editor

Kami merekomendasikan gunakan Sublime Text. Kemudian Code Editor lain yang bisa digunakan adalah Atom.

Bahasa Ruby sangat spesifik dan memilki keunikan sendiri dimana membuat Ruby mudah dibaca dan menuliskannya untuk semua orang. Setelah mempelajari beberapa saat anda akan terbiasa dengan sintaks Ruby.

* Text editor harus di set 2 spasi.

* Tanda # di awal line adalah komentar. Komentar digunakan oleh programmer untuk menuliskan catatan untuk programmer lain atau diri nya sendiri pada saat membukanya kembali beberapa waktu.

Pada saat men define atau initialize sebuah method, variable, atau file, anda harus selalu menggunakan "**snake_case formatting**". snake_case formatting adalah semua character menggunakan lower case dan dipisahkan dengan underscore character. Contoh:

Nama file:

	this_is_a_snake_cased_file.rb

Assigning a variable

	forty_two = 42

Defining a method

	def this_is_a_great_method
	  # do stuff
	end

* Pada saat anda membuat value yang tidak berubah ubah pada Ruby program, anda define sebuah **constant variable**, sering disebut **constant**. Di Ruby, constant ditandai dengan huruf besar semua.

Constant declaration
	
	FOUR = 'four'
	FIVE = 5

* Pada saat menggunakan do/end blocks, lebih baik menggunakan { } saat seluruh code expression fit dalam satu baris.

Multi-line

	[1, 2, 3].each do |i|
		# do stuff
	end

Sama juga bila gunakan single line

	[1, 2, 3].each { |i| # do stuff }

* Cara men declare a class name. Saat memberi nama classes gunakan **CamelCase formatting**, tanpa spasi capitalizes setiap kata.

Class naming

    class MyFirstClass
	end

	class MySecondClass
	end

[Ruby style guide](https://github.com/bbatsov/ruby-style-guide)

---

### Cara membaca dokumentasi Ruby

Hal yang paling penting menjadi Ruby programmer dan menjadi kebiasaan yang sangat penting yang harus anda kembangkan adalah bagaimana **cara membaca dokumentasi** Ruby. Ruby memiliki standard yang sangat kaya yang dapat anda gunakan. Anda perlu mempelajari Ruby documentation - atau Ruby docs - untuk mendapatkan pemahaman tentang perbedaan classes dan methods.  

> Be aware that some developers also refer to documentation as API. API is an acronym for application programming interface, and is a somewhat overloaded term that can refer to both how applications talk to each other, as well as documentation. Just remember, if someone says "Did you take a look at the Array API?", they're talking about the Ruby docs documentation for the Array class. But if someone says "What's the Twitter API?", they're talking about the programmatic interface to Twitter's services.

![ruby-doc](http://res.cloudinary.com/medioxtra/image/upload/v1492443417/string_ojzeuy.png)

### Class name atau Module name

In the first circle at the top, we see the word "String". This is the Class or Module (again, don't worry about what that is just yet, we will eventually cover it). In some documentation, you'll see the class name being referred to with a :: symbol, like this: Encoding::Converter. Here, the :: symbol is used to define a namespace, which is just a way to group classes in Ruby and differentiate from other classes with the same name. For example ActiveRecord::Base is referring to the Base class in the ActiveRecord module, to differentiate from other classes also named Base. However, when looking at the method list on the side bar, the :: means something different: it means that the method after the :: is a class method - we'll talk about this more later. For now, just realize that whether the top heading says String or Encoding::Converter, it's referring to the class or module name and the rest of the page will be documenting that class or module.

### Methods

Method dalam dokumentasi di tulis sebagai **::** atau **#** untuk membedakan jenis publik akses methodnya adalah **::** digunakan sebagai **class methods**, dan **#** digunakan sebagai **instance methods**.

Tetapi diluar dokumentasi jangan sampai keliru dengan simbol tersebut diatas karena pada saat menulis Ruby code bisa berarti berbeda, contoh simbol **::** digunakan sebagai **namespace** dalam Ruby code, dan simbol **#** digunakan sebagai **komentar**. Jadi Ruby documentation completely berbeda dari actual code yang digunakan.

We can look at the string "world wide web" and directly apply instance methods. we see that there's a **#split** method for strings, which means that split is an **instance method**, and we can call that method on any string directly:

	dyo@ubuntu:~$ irb
	2.4.0 :001 > "satyo bagus widyo bumi".split
	 => ["satyo", "bagus", "widyo", "bumi"] 
	2.4.0 :002 >

Kemudian kita bisa lihat ada dua class methods: **::new** dan **::try_convert**, Public Class Methods bisa dipanggil langsung dari class.	 

	2.4.0 :001 > b = String.new("blue")
	 => "blue" 
	2.4.0 :002 > b = String.try_convert("red")
	 => "red" 
	2.4.0 :003 > b
	 => "red" 

### Parent

Pada Ruby setiap class dan sub-classes berasal dari beberapa "parent". Untuk memahami ini anda perlu paham mengenai **object oriented programming** (akan dibahas kemudian). Yang perlu dipahami saat ini adalah **class** memiliki akses ke methods - **instance** dan **class**.

Contoh dalam hal ini adalah **String class's parent adalah Object**.

Ini artinya method dari Object juga tersedia untuk strings. (This section of the page will link to the parent's documentation and is a good followup read if you aren't familiar with the parent object or you aren't finding methods you'd expect to see).

### Summary

> In this section we looked at Ruby's documentation. When in doubt, review the Ruby docs at www.ruby-doc.org that match the version of Ruby you are working with, and learn to get familiar with reading Ruby documentation. It should become a normal part of your workflow.

---

### Belajar menggunakan Command Line dan irb

#### Command Line

To create a directory (or folder) called 'new_dir' type the following command:

	$ mkdir new_dir

To navigate into the folder you just created:

	$ cd new_dir

To create a file called 'new_file':

	$ touch new_file.rb

To delete the file you just created:

	$ rm new_file.rb

To navigate out of the current folder to the one above:

	$ cd ..

To delete the directory you just created:

	$ rmdir new_dir

Now, create the directory and file like you did above, again.

To remove the directory and file at the same time navigate to the directory above 'new_dir' and type the following command:

	$ rm -R new_dir

Hati-hati dengan **rm** command. Sangat destructive dan tidak dapat di recover lagi. Bila ragu gunakan folder / file navigasi program (e.g. Explorer or Finder) dan hapus dengan cara seperti biasa.

#### irb

Ruby has a built in interactive environment called "irb" that can be very helpful when writing Ruby code. At the command line type:

	$ irb

This will produce a prompt that looks something like this:

	2.0.0p-247 :001 >

The 2.0.0p-247 is telling us what version of Ruby we are running and the :001 tells us what line we are on. However, throughout this book, we will refer to the irb prompt like this:

	irb :001 >

You can type in a Ruby command after the prompt and see its output and what it returns. For example, if you type the following command and press return to run it:

	irb :001 > puts 'hello world!'

The output will look something like this:

	irb :001 > puts 'hello world!'
	hello world!
 	=> nil
	irb :002 >

When you want to exit irb back to the command line, just type exit. 

### Running Ruby Code

Pada saat membuat Ruby file, simpan dengan **.rb** extension, anda dapat menjalankan code pada file tersebut dengan mengetik "ruby" diikuti nama file dan extentionnya, contoh file example.rb.

	$ ruby example.rb

Asumsi file example.rb file memuat code baris puts 'hello world!'.

	$ ruby example.rb
	hello world!
	$

When you run a Ruby file from the command line, the code gets executed by what's called an interpreter.

To exit out of the program execution loop, use control-c.

#### Perlu di ingat!

Pastikan anda sudah mengerti perbedaan dari tiga hal diatas:

1. Menggunakan Command untuk me-manage files dan folders pada command line (terminal).
2. Menggunakan Ruby commands di irb.
3. Menggunakan Ruby code dari **.rb** file pada command line.

## Ruby "Gems"

### Apa itu Gems?

Rubyists (sebutan untuk para developer Ruby) menyebutnya **RubyGems** atau **"gems"** saja. Ada dua definisi dari RubyGems: 

* Satu, adalah sebagai kumpulan dari file-file Ruby atau **Ruby library**, yang memiliki tugas/fungsi tertentu. 
* Dua, sebagai **publishing system** adalah sebagai organisasi, listing, dan publishing librari, atau gems, yang anda bisa download, untuk anda gunakan pada system anda. Anda bisa lihat dan download librari tersebut yang disebut **"gems"**. di website [rubygems.org.](http://rubygems.org). 

RubyGems secara default untuk membantu para developer Ruby mengembangkan aplikasi dengan lebih cepat. code didalam gem seperti **pre-packaged bundles** dari code yang ditulis oleh seseorang untuk memecahkan solusi yang berguna, menghemat waktu pengerjaan. Ruby gems have versions based on the Semantic Versioning standard. Seluruh public instal gems ada di [rubygems.org.](http://rubygems.org) dan code nya di host di code repository, seperti a Github.com.

Cara menggunakan:

	gem install <nama gem>

### Debugging Ruby code with Pry

Pry adalah library yang bagus sebagai alternative untuk irb dengan host features menarik. Untuk menggunakan pry kita harus meng-instal nya:

	gem install pry

This gives you the pry command which when entered in your terminal will open a new session just like you would with irb.

Use pry for debugging

Next, when you want to use pry for debugging you'll have to require "pry" and insert a binding.pry in your file like so:

Use pry for debugging

Next, when you want to use pry for debugging you'll have to require "pry" and insert a binding.pry in your file like so:

	#preparation.rb
	
	require "pry"

	a = [1, 2, 3]
	a << 4
	binding.pry     # execution will pause here, allowing you to inspect all objects
	puts a

> What this means is that when your program gets to where binding.pry has been declared, it'll open a new pry session instead of moving on to the next line in the code. This gives you the opportunity to play around with your variables and objects to see why things are not working. This is an extremely powerful debugging technique since it lets you pause execution to inspect the state of all variables and objects at that line of code. After you're done looking at your variables, you can continue the program execution with Ctrl + D.

> We've just scratched the surface of what you should know to debug simple Ruby code. We just want to introduce you to this debugging technique in Ruby because it's a better alternative to using puts for debugging and gives you a good idea of what's really happening within your code.

#### Exercises

1. Create a directory named my_folder and then navigate inside that directory. Create two files named one.rb and two.rb in the my_folder directory. Write a ruby program that outputs the line this is file one when you run the one.rb file. Then write another program that outputs this is file two when you run the two.rb file. (Hint: one.rb should have this in it puts "this is file one")

2. 


---

## Basic Ruby

### Strings

String adalah kumpulan dari karakter secara spesifik berurutan. String tulis dengan single quote ('hi there') atau double quote ("hi there").

Jika menggunakan single quote, anda bisa menggunakan double quote method atau menggunakan single quote method dengan **escaping**:

Ex. 1: with double quotes

	"The man said, 'Hi there!'"

Ex 2: with single quotes and escaping

	'The man said, \'Hi there!\''

**Backslash** atau **escape** (\)** karakter, tells the computer that the quotes that follow it are not meant as Ruby syntax but only as simple quote characters to be included in the string.

Double quotes allow something called string interpolation. To try it out, type the following into an irb session:	

	irb :001 > a = 'ten'
	 => "ten" 
	irb :002 > "My favorite number is #{a}!"
	 => "My favorite number is ten!"

String interpolation is a handy way to merge Ruby code with strings. The basic syntax is: #{ruby expression goes here}, and the returned expression will be concatenated with the surrounding string. String interpolation only works within double quotes. You'll get quite familiar with this technique over time.

### Symbol

Ruby symbols adalah menempatkan colon (:) didepan kata.

Examples of symbols

	:nama
	:a_symbol
	:"ini juga symbol"

Basically, a symbol is used when you want to reference something like a string but don't ever intend to print it to the screen or change it. It is often referred to as an immutable (i.e. unchangeable) string.

### Numbers

Numbers me-representasikan banyak cara pada Ruby. Yang paling dasar adalah untuk memanggil integer. Dimana me-representasikan seluruh number tanpa tanda desimal. Sangat komplek number kita sebut float. Float adalah number yang memuat desimal.

Example of integers

	1, 2, 3, 50, 10, 4345098098

Example of floats

	1.2345, 2345.4267, 98.2234

### Nill

In programming, we need a way to express "nothing", and in Ruby, we do this through something called nil. A variable with a value of nil could be described as having 'nothing' or being 'completely empty', or even just simply 'not any specific type'. A situation where this may occur is where output is expected but none is returned, such as:

	irb :001 > puts "Hello, world!"
	 Hello, world!
	 => nil 

The puts method prints out a string and returns nothing, so we see nil being returned after the string is displayed.

It is possible to check if something is a nil type by using .nil?. For example:

	irb :001 > "Hello, World".nil?
	=> false

### Operation

Operasi matematika Tambah (Adding), Kurang (Subtracting), dan Perkalian (Multiplying Integers)

Gunakan irb untuk latihan:

	dyo@ubuntu:~$ irb
	2.4.0 :001 > 1-1
	 => 0 
	2.4.0 :002 > 4*4
	 => 16 
	2.4.0 :003 > 5-6
	 => -1 

#### Division vs. Modulus

Pembagian gunakan **/** operator, contoh:

	dyo@ubuntu:~$ irb
	2.4.0 :001 > 16/4
	 => 4 

Modulus atau modulo gunakan **%** operator, Modulo adalah **hasil sisa dari sebuah pembagian integer**, contoh:

	dyo@ubuntu:~$ irb
	2.4.0 :001 > 16 % 4
	 => 0  
	2.4.0 :003 > 16 % 5
	 => 1 

#### Multiplying and Dividing Floats

Untuk mendapatkan hasil akurasi dari operasi pembagian kita bisa gunakan floats.

	dyo@ubuntu:~$ irb
	2.4.0 :001 > 15.0 / 4
	 => 3.75

Untuk perkalian yang kompleks gunakan **multiply floats**.

	dyo@ubuntu:~$ irb
	2.4.0 :001 > 9.75 * 3.45
	 => 33.6375 

#### Equality Comparison

Equality Comparison adalah ketika anda ingin mengecek jika nilai nilai dari dua object adalah sama. equality dari dua nilai tersebut gunakan **== operator**. Ini akan membandingkan object sebelah kiri dari operator == dengan object sebelah kanannya dan hasilnya (return) antara **true** or **false**, true dan false disebut nilai **boolean**. Gunakan irb untuk latihan:

	dyo@ubuntu:~$ irb
	2.4.0 :001 > 4 == 4
	 => true 
	2.4.0 :002 > 4 == 5
	 => false 
	2.4.0 :003 > 'foo' == 'foo'
	 => true 
	2.4.0 :004 > 'foo' == 'bar'
	 => false 

Apa yang terjadi bila dibawah ini:

	2.4.0 :005 > '4' == 4
	 => ???

#### String Concatenation

String concatenation seperti sebuah operasi penjumlahan. Menggunakan **+** operator untuk menggabungkan dua buah string, gunakan irb! :

	dyo@ubuntu:~$ irb
	2.4.0 :001 > 'foo' + 'fii'
	 => "foofii" 
	2.4.0 :002 > 'foo' + 'bar'
	 => "foobar" 
	2.4.0 :003 > 'Dyo' + '' + 'Medio'
	 => "DyoMedio" 
	2.4.0 :004 > 'Dyo' + ' ' + 'Medio'
	 => "Dyo Medio" 

Cobalah bermain-main dengan irb:

	dyo@ubuntu:~$ irb
	2.4.0 :001 > '1'+'1'
	 => "11" 
	2.4.0 :002 > 'satu' + '1'
	 => "satu1" 
	2.4.0 :003 > 'satu' + 1
	TypeError: no implicit conversion of Integer into String
		from (irb):3:in `+'
		from (irb):3
		from /home/dyo/.rvm/rubies/ruby-2.4.0/bin/irb:11:in `<main>'

Pada latihan irb **'satu' + 1** muncul pesan error. Iinterpreter tidak dapat secara langsung mengconversin nilai **Fixnum** menjadi nilai **String**. Kita tidak dapat menggabungkan Fixnum dan String bersama. By the way, FixNum adalah sebuah nilai integer.

#### Type Conversion

Untuk menggabungkan String dan Fixnum, contoh '12' + 2, akan menghasilkan error.

Untuk menggabungkan gunakan sebuah **method** yang meng-convert String to Fixnum, dengan menggunakan **to_i**, pada setiap String, perhatikan contoh dibawah:

	dyo@ubuntu:~$ irb
	2.4.0 :001 > '4'.to_i
	 => 4 
	2.4.0 :002 > '4 hello dyo'.to_i
	 => 4 
	2.4.0 :003 > 'helo dyo 4'.to_i
	 => 0 
	2.4.0 :004 > '4'.to_f
	 => 4.0 
	2.4.0 :005 > '4 hello dyo'.to_f
	 => 4.0 
	2.4.0 :006 > 'hello dyo 4'.to_f
	 => 0.0 

Contoh berikutnya:

	2.4.0 :007 > '5'.to_s
	 => "5" 
	2.4.0 :008 > 'hello dyo 4'.to_s
	 => "hello dyo 4" 
	2.4.0 :009 > '4 hello dyo'.to_s
	 => "4 hello dyo" 
	2.4.0 :010 > 4 + '5'.to_s
	TypeError: String can't be coerced into Integer
		from (irb):10:in `+'
		from (irb):10
		from /home/dyo/.rvm/rubies/ruby-2.4.0/bin/irb:11:in `<main>'
	2.4.0 :011 > 4 + 5.to_s
	TypeError: String can't be coerced into Integer
		from (irb):11:in `+'
		from (irb):11
		from /home/dyo/.rvm/rubies/ruby-2.4.0/bin/irb:11:in `<main>'
	2.4.0 :012 > '4' + 5.to_s
	 => "45"

Tugas: Jelaskan kenapa terjadi error? Kenapa '4' + 5.to_s tidak error?

## Basic Data Structures

Dua data struktur yang paling umum anda gunakan pada Ruby adalah **array** dan **hash**. Akan dijelaskan lebih detil kemudian tapi sekarang kita akan berkenalan terlebih dahulu.

### Arrays

Sebuah aray digunakan untuk mengorganisasikan informasi kedalam bentuk daftar yang berurutan. Daftar ini bisa terdiri dari string, integer, float, boolean, atau tipe data lainnya. Pada Ruby array ditandai dengan square brackets (kurung kotak) **[ ]**. Didalam bracket anda dapat memembuat daftar element yang dipisahkan dengan tanda koma "**,**" mari kita coba di irb.

	dyo@ubuntu:~$ irb
	irb :001 > [1,2,3,4,5]
	 => [1, 2, 3, 4, 5]	
 
Diatas kita membuat array of integer 1 sampai 5. Tiap element dalama array dapat di akses via **index**. Index adalah sebuah nomor urut yang dimulai dari **nol** (zero). Akses hanya pada element pertama kita dapat lakukan begini:

	irb :001 > [1,2,3,4,5]
	 => [1, 2, 3, 4, 5] 
	irb :002 > [1,2,3,4,5][0]
	 => 1

	irb :003 > [1,2,3,4,5][2]
	 => 3 
	irb :004 > [1,2,3,4,5][1]
	 => 2 

### Hashes

Hash, kadang disebut **dictionary**, hash adalah pasangan dari **key-value**. Hash ditandai dengan **curly braces { }**. Pada sebuah pasangan **key-value** dimana key menunjuk kepada sebuah nilai tertentu. 

Sebuah hash terdiri dari sebuah kunci, biasanya ditunjukkan oleh sebuah simbol, yang menunjukkan nilai (dilambangkan dengan menggunakan a =>) dari semua jenis data.

	irb :001 > {:dog => 'barks'}
	 => {:dog=>"barks"}

Diatas adalah hash dengan satu pasang key-value. Sama seperti array, kita dapat memiliki multiple items pada hash jika kita pisahkan mereka dengan tanda "koma":

	irb :002 > {:anjing => 'menggonggong', :kucing => 'mengeong', :ayam => 'berkokok'}[:kucing]
	 => "mengeong"


---


6. Type Conversion
7. Basic Data Structures
8. Expressions and Return
9. puts vs return
10. Latihan

## Variables

1. Apa itu variable?
2. Menetapkan Nilai untuk Variables
3. Mendapatkan Data dari User
4. Variable Scope
5. Types of Variables
6. Latihan

## Method

1. Apa itu Method?
2. Object Method
3. Mutating the Caller
4. puts vs return
5. Chaining Methods
6. Methods as Arguments
7. Latihan

## Flow Control

1. Conditionals
2. Comparisons
3. Combining Expressions
4. Ternary Operator
5. Case Statement
6. True and False
7. Latihan

## Loops & Iterators

1. A Simple Loop
2. Controlling Loop Execution
3. While Loops
4. Until Loops
5. Do/While Loops
6. For Loops
7. Conditionals Within Loops
8. Iterators
9. Recursion
10. Latihan

## Array
..
dll

## Hashes
..
dll

## More
1. Regex
..
dll



