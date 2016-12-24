#Rails Routes

#### Penulisan block member acton, di gunakan apabila ada penambahan apapun dari book, agar sediakan routes 

	resources :books do
		member do
		  patch :publish
		end
	end