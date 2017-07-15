# Each User Own Post:

Controller

	def new
		@post = Post.new
		@post = current_vendor.posts.build
	end

	def create
		@post = Post.new(post_params)
		@post = current_vendor.posts.build(post_params)
	...

Hanya bisa melihat post nya masing2

	def index
		if current_vendor.supervendor
	      @posts = Post.all.order("created_at DESC")
	    else  
	      @posts = Post.where(:vendor_id => current_vendor.id).order("created_at DESC")
	    end
	end


If error because we dont have vendor_id in table posts

	Mysql2::Error: Unknown column 'posts.vendor_id' in 'where clause': SELECT `posts`.* FROM `posts` WHERE `posts`.`vendor_id` = 2  ORDER BY created_at DESC
	 
solution :

	rails generate migration add_vendor_id_to_posts vendor_id:integer

	and rake db:migrate