### Define resource actions that require authentication using routes.rb

https://github.com/plataformatec/devise/wiki/How-To:-Define-resource-actions-that-require-authentication-using-routes.rb

  authenticate :user do
    resources :mcblogs, only: [:index, :new, :create, :edit, :update, :destroy], path: 'admin/mcblogs'
  end
  resources :mcblogs, only: [:show]

  authenticate :user do
		scope "/admin" do
  		resources :mcblogs, only: [:index, :new, :create, :edit, :update, :destroy]
		end
	end
	resources :mcblogs, only: [:show]  