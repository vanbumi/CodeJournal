# Filter dan Pencarian di Ruby on Rails
[sumber](http://agung-setiawan.com/filter-dan-pencarian-di-ruby-rails/)


Rails punya where dan juga scope yang bisa digunakan untuk kasus pencarian serta filter kali ini. Akan saya bahas di artikel ini.
Struktur Tabel

Pada artikel ini saya menggunakan 2 buah tabel yang berelasi yaitu tabel categories dan products. Strukturnya sederhana, bisa dilihat di bawah ini.

	categories
	-------------------
	id:integer
	name:string
	description:text
	created_at:timestamp
	updated_at:timestamp
	 
	products
	--------------------
	id:integer
	name:string
	price:integer
	rating:integer
	description:text
	category_id:integer
	created_at:timestamp
	updated_at:timestamp


Untuk kelasnya

	class Category < ActiveRecord::Base
	  has_many :products
	end
	
	class Products < ActiveRecord::Base
	  belongs_to :category
	end	

## where

where di Rails kegunaannya sama dengan klausa WHERE yang ada di SQL yaitu untuk melakukan filtering terhadap data yang kita punya. Misal untuk mencari data produk yang kategori id bernilai 1 maka digunakan where seperti ini.

	Product.where(category_id: 1)
	 
	SELECT `products`.* FROM `products` WHERE `products`.`category_id` = 1

Contoh lain untuk mencari produk yang memiliki rating 5

	Product.where(rating: 5)
	 
	SELECT `products`.* FROM `products` WHERE `products`.`rating` = 5


Intinya adalah parameter hash yang digunakan berarti key menandakan nama kolom sebagai dasar penyaringan dan value-nya sebagai nilai untuk penyaringan.

where ini bisa disambung atau istilahnya chaining untuk mendapatkan hasil penggabungan lebih dari satu kondisi. Dalam SQL ini berarti penggunaan AND

	Product.where(category_id: 1).where(rating: 5)
	 
	SELECT `products`.* FROM `products` WHERE `products`.`category_id` = 1 AND `products`.`rating` = 5

Bagaimana untuk pencarian?, gabungkan saja dengan klausa LIKE seperti ini.
	
	Category.where('name like ?', '%progr%')
 
	SELECT `categories`.* FROM `categories` WHERE (name like '%progr%')

Penggunaan where di Rails dasarnya adalah sesimpel itu. Untuk mengetahui fitur yang lebih lengkap dari where silakan kunjungi dokumentasi resminya.

## Controller

Controller adalah jalan masuk untuk parameter-parameter filter dan pencarian yang dimasukkan oleh pengguna. Oleh karena itu, kita perlu memanggil kode yang melakukan pencarian di dalam controller. Contohnya seperti ini.

class ProductsController < ApplicationController
  
  def index
    @products = Product.where(nil)
    @products = @products.where(category_id: params[:category]) if params[:category].present?
    @products = @products.where(rating: params[:rating]) if params[:rating].present?
    @products = @products.where('name like ?', "%#{params[:thename]}%") if params[:thename].present?
  end
end

Kondisi diperlukan karena bisa saja pengguna tidak menggunakan semua filter yang ada sehingga kita harus menyesuaikan filter mana yang memang digunakan. Ada kemungkinan juga pengguna sama sekali tidak melakukan pemfilteran.

Dan sekarang kita bisa menggunakan filter dan pencarian menggunakan query parameter.

http://example.com/products?rating=5&category=1&thename=ruby
1
	
http://example.com/products?rating=5&category=1&thename=ruby

scope

Kode pencarian dan filter kita di atas akan lebih baik jika proses filter dan pencariannya tidak berada langsung di controller karena fungsi dari controller bukanlah untuk itu. Untuk itu, mari kita gunakan scope untuk membuat method yang menangani filter serta pencarian produk.

class Products < ActiveRecord::Base belongs_to :category scope :rating, -> (rating) { where(rating: rating) } scope :category, -> (category) { where(category_id: category) } scope :thename, -> (name) { where('name like ?', "%#{name}%") } end
1
2
3
4
5
6
7
	
class Products < ActiveRecord::Base
  belongs_to :category
 
  scope :rating, -> (rating) { where(rating: rating) }
  scope :category, -> (category) { where(category_id: category) }
  scope :thename, -> (name) { where('name like ?', "%#{name}%") }
end

Scope ini pada dasarnya membuat kelas method untuk kita sehingga misalnya scope rating diubah menjadi kelas method seperti ini hasilnya akan sama.

class Products < ActiveRecord::Base belongs_to :category scope :category, -> (category) { where(category_id: category) } scope :thename, -> (name) { where('name like ?', "%#{name}%") } def self.rating(rating) where(rating: rating) end
1
2
3
4
5
6
7
8
9
	
class Products < ActiveRecord::Base
  belongs_to :category
 
  scope :category, -> (category) { where(category_id: category) }
  scope :thename, -> (name) { where('name like ?', "%#{name}%") }
 
  def self.rating(rating)
    where(rating: rating)
  end

Sebenarnya ada beda antara scope dengan kelas method, saya bahas di artikel selanjutnya saja 🙂

Nah dengan sudah adanya scope ini kita bisa merapikan kodingan yang ada di controller menjadi seperti berikut.

class ProductsController < ApplicationController def index @products = Product.where(nil) @products = @products.category(params[:category]) if params[:category].present? @products = @products.rating(params[:rating]) if params[:rating].present? @products = @products.thename(params[:thename]) if params[:thename].present? end end
1
2
3
4
5
6
7
8
9
	
class ProductsController < ApplicationController
  
  def index
    @products = Product.where(nil)
    @products = @products.category(params[:category]) if params[:category].present?
    @products = @products.rating(params[:rating]) if params[:rating].present?
    @products = @products.thename(params[:thename]) if params[:thename].present?
  end
end

Lebih Rapi Lagi

Masih bisakah kode kita menjadi lebih rapi lagi?
Bisa!

Dengan memanfaatkan nama parameter yang sama dengan nama scope, kita bisa menggunakan perulangan untuk mengubah kode menjadi seperti di bawah ini. Kunci utamanya selain nama parameter sama dengan nama scope adalah penggunaan method send.

class ProductsController < ApplicationController def index @products = Product.where(nil) filter_params(params).each do |key, value| @products = @products.send(key, value) if value.present? end end private def filter_params(params) params.slice(:category, :rating, :thename) end end
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
	
class ProductsController < ApplicationController
  
  def index
    @products = Product.where(nil)
    filter_params(params).each do |key, value|
      @products = @products.send(key, value) if value.present?
    end
  end
 
  private
 
  def filter_params(params)
    params.slice(:category, :rating, :thename)
  end
end

Bagi yang belum tahu, send adalah method yang digunakan untuk memanggil method. Contohnya seperti ini.

category = Category.first category.send(:name) #sama dengan category.name
1
2
	
category = Category.first
category.send(:name) #sama dengan category.name

Parameter pertama adalah berupa simbol atau string yang merupakan nama dari method yang dipanggil. Parameter kedua dan seterusnya adalah parameter bagi method yang dipanggil pada parameter pertama. Hmm lumayan membingungkan kalimatnya, langsung contoh saja ya.

class Calculator def add(a, b) a + b end end
1
2
3
4
5
	
class Calculator
  def add(a, b)
    a + b
  end
end

Menggunakan send untuk memanggil method add maka bentuknya seperti ini.

calc = Calculator.new result = calc.send(:add, 5, 10) #=> 15
1
2
3
	
calc = Calculator.new
result = calc.send(:add, 5, 10)
#=> 15

Sekarang dengan sudah mengerti bagaimana cara kerja send bisa dong memahami bagaimana @products.send(key, value) if value.present? bekerja? 😉

Ah satu lagi, merasa janggal kenapa nama scope yang saya gunakan bernama thename bukan name?

Hal ini karena Rails sudah memberikan kelas method bernama name untuk setiap kelas dari active record sehingga jika kita membuat scope bernama name akan menyebabkan error.

Dan kemudian kenapa nama parameter yang digunakan adalah thename juga ya karena biar bisa menggunakan @products.send(key, value) if value.present? memanfaatkan nama scope yang sama dengan nama parameter.




