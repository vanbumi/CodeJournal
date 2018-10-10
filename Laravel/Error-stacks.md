# Error stacks Laravel

> Could not find package laravel/laravel with version 5.4.* in a version inst  
  allable using your PHP version 5.5.38.

**solutions**

https://stackoverflow.com/questions/37873586/could-not-find-package-laravel-laravel-with-stability-stable


...

> Syntax error or access violation: 1071 Specified key was too long; max key length is 767 bytes (SQL: alter table users add...

**Solutions**

As outlined in the Migrations guide to fix this all you have to do is edit your AppServiceProvider.php file and inside the boot method set a default string length:

use Illuminate\Support\Facades\Schema;

	public function boot()
	{
			Schema::defaultStringLength(191);
	}
	
https://laravel-news.com/laravel-5-4-key-too-long-error
