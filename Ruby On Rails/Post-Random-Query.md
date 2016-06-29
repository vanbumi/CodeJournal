# Random Posts Query

Basic

	@posts = Post.all.sample(10)

	@posts_cities = Post.all.sample(4)

With if condition

	@posts_cities = Post.all.where("status = ?", "Publish").sample(4)