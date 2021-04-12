### Scaffold command

	rails generate scaffold article title:string body:text

	rake db:migrate

## Rails Conventions – Singular or Plural?

Controller		Plural		rails g controller Users index show
Helper			Plural		rails g helper Users
Mailer			Singular	rails g mailer UserMailer
Migration		Plural		rails g migration AddEmailToUsers email:string
Model			Singular	rails g model User name:string
Observer		Singular	rails g observer User
Resource		Plural*		resources :users, :only => [:index, :show]
Scaffold		Singular	rails g scaffold User name:string
Table			Plural		SELECT * FROM users;
View			N/A	app/views/users/index.html.erb – comprised of controller (plural) and action (singular)	