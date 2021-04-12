# Rails Routes

#### Penulisan block member acton, di gunakan apabila ada penambahan apapun dari book, agar sediakan routes 

	resources :books do
		member do
		  patch :publish
		end
	end

#### Match

	match "users/:id/upload", to: "users#upload", via: :get

Atau, contoh lain:

	get "users/:id/upload" => "users#upload", :as => "users/:id/upload" 		