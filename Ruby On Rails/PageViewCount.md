# Page Impression

### Source:

[impressionist-github](https://github.com/charlotte-ruby/impressionist)

### Logs an impression

**Logs Impression** adalah menghitung berapa kali (me-log) halaman ditampilkan atau dibaca oleh pengunjung. 

* It can log page impressions (technically action impressions)
* You can log impressions multiple times per request.
* And you can also attach it to a model.

> The goal of this is to provide **customizable stats** that are immediately accessible in your application as opposed to using Google Analytics and pulling data using their API.

##### Installation

Add it to your Gemfile

	gem 'impressionist'

Install with Bundler

	bundle install

Generate the impressions table migration

	rails g impressionist

Run the migration

	rake db:migrate

It does generate table below:	

	class CreateImpressionsTable < ActiveRecord::Migration
	  def self.up
	    create_table :impressions, :force => true do |t|
	      t.string :impressionable_type
	      t.integer :impressionable_id
	      t.integer :user_id
	      t.string :controller_name
	      t.string :action_name
	      t.string :view_name
	      t.string :request_hash
	      t.string :ip_address
	      t.string :session_hash
	      t.text :message
	      t.text :referrer
	      t.timestamps
	    end
	    add_index :impressions, [:impressionable_type, :message, :impressionable_id], :name => "impressionable_type_message_index", :unique => false, :length => {:message => 255 }
	    add_index :impressions, [:impressionable_type, :impressionable_id, :request_hash], :name => "poly_request_index", :unique => false
	    add_index :impressions, [:impressionable_type, :impressionable_id, :ip_address], :name => "poly_ip_index", :unique => false
	    add_index :impressions, [:impressionable_type, :impressionable_id, :session_hash], :name => "poly_session_index", :unique => false
	    add_index :impressions, [:controller_name,:action_name,:request_hash], :name => "controlleraction_request_index", :unique => false
	    add_index :impressions, [:controller_name,:action_name,:ip_address], :name => "controlleraction_ip_index", :unique => false
	    add_index :impressions, [:controller_name,:action_name,:session_hash], :name => "controlleraction_session_index", :unique => false
	    add_index :impressions, :user_id
	  end

	  def self.down
	    drop_table :impressions
	  end
	end

## Usage

1. Log all actions in a controller

		class ArticlesController < ApplicationController

  			impressionist
			...
		
		end	

2. Specify actions you want logged in a controller

		class NewsController < ApplicationController

  			impressionist :actions=>[:show,:index]
  			...
		
		end

3. Make your models impressionable. This allows you to attach impressions to an AR model instance. Impressionist will automatically log the Model name (**based on action_name**) and the id (**based on params[:id]**), but in order to get **the count of impressions** (example: **@widget.impression_count**), you will need to make your model **impressionable**

		class Article < ApplicationRecord

		  is_impressionable
		  ...

		end	

4. Log an impression per model instance in your controller. Note that it is not necessary to specify "impressionist" (usage #1) in the top of you controller if you are using this method. If you add "impressionist" to the top of your controller and also use this method in your action, it will result in 2 impressions being logged (but associated with one request_hash). If you're using friendly_id be sure to log impressionist this way, as params[:id] will return a string(url slug) while impressionable_id is a Integer column in database.
*Log impression permodel instance pada controller anda. Catatan: tidak perlu menambahkan "impresionist" (pada step 1) di baris atas controller bila menggunakan step 4 ini. Jika anda menambahkan "impressionist" di baris atas controller dan juga menggunakan step 4, ini akan mengahasilkan 2 impressions (tapi di relasikan dengan satu request_hash). Jika anda menggunakan friendly_id pastikan untuk melakukan log impressionist pada step 4 ini, sebagai params[:id] akan menghasilkan string (url slug) sementara impressionable_id adalah integer di kolom database.*

		def show
		  @article = Article.find
		  impressionist(@article, "message...") # 2nd argument is optional
		end

Note: Use this step for controller with no model (frontend), example my article_controller and my news_controller. 		

5. Get unique impression count from a model. This groups impressions by request_hash, so if you logged multiple impressions per request, it will only count them one time. This unique impression count will not filter out unique users, only unique requests.

View Show:
		
		@article.impressions.count
		@article.impressions.count(:start_date=>"2011-01-01",:end_date=>"2011-01-05")
		@article.impressions.count(:start_date=>"2011-01-01")  #specify start date only, end date = now

View Index:

		<% @articles.each do |article| %>
		   <%= article.impressions.count %> 
		<% end %> 		

> Error : undefined method `impressionist_count' for nil:NilClass
**solution**: has change to impressions.count	
> Error : wrong number of arguments (given 2, expected 0..1)
**solution**: <%= article.impressions.count %>

---
	

#### How to Query

[Stack-Overflow most-viewed-items-using-impressionist-gem](http://stackoverflow.com/questions/25565621/last-week-most-viewed-items-using-impressionist-gem)

	Post.joins(:impressions).where("impressions.created_at<='#{Time.now}' and impressions.created_at >= '#{start_time}'").group("impressions.impressionable_id").order("count(impression‌​s.id) DESC")

Case on wb sites:

	@posts_hits = Post.joins(:impressions).group("impressions.impressionable_id").order("count(impressionable_id) DESC").limit(5)	


[Stack-Overflow get-impresions-count-from-today-yesterday-and-this-month](http://stackoverflow.com/questions/27549386/get-impresions-count-from-today-yesterday-and-this-month-impresionist-gem)	