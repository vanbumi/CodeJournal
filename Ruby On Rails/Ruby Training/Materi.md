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

	# Constant declaration
	
	 FOUR = 'four'
	 FIVE = 5

* Pada saat menggunakan do/end blocks, lebih baik menggunakan { } saat seluruh code expression fit dalam satu baris.

	# Multi-line
	[1, 2, 3].each do |i|
		# do stuff
	end

	# Sama juga bila gunakan single line
	[1, 2, 3].each { |i| # do stuff }

* Cara men declare a class name. Saat memberi nama classes gunakan **CamelCase formatting**, tanpa spasi capitalizes setiap kata.

	# Class naming

    class MyFirstClass
	end

	class MySecondClass
	end

[Ruby style guide](https://github.com/bbatsov/ruby-style-guide)

---

### Documentation

Hal yang paling penting menjadi Ruby programmer dan menjadi kebiasaan yang sangat penting yang harus anda kembangkan adalah bagaimana **cara membaca dokumentasi** Ruby. Ruby memiliki standard yang sangat kaya yang dapat anda gunakan. Anda perlu mempelajari Ruby documentation - atau Ruby docs - untuk mendapatkan pemahaman tentang perbedaan classes dan methods.  

> Be aware that some developers also refer to documentation as API. API is an acronym for application programming interface, and is a somewhat overloaded term that can refer to both how applications talk to each other, as well as documentation. Just remember, if someone says "Did you take a look at the Array API?", they're talking about the Ruby docs documentation for the Array class. But if someone says "What's the Twitter API?", they're talking about the programmatic interface to Twitter's services.



### Belajar menggunakan Command Line dan irb

### Apa itu Gems?

### Debug Ruby code dengan Pry

## The Basics

1. Strings
2. Symbols
3. Numbers
4. Nill
5. Operation
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



