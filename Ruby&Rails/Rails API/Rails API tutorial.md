# Rails API

* [Using Rails for API-only Applications - Rails Guides](http://edgeguides.rubyonrails.org/api_app.html)

* [Build an API in your Rails app now!](https://labs.kollegorna.se/blog/2015/04/build-an-api-now/) 

## Using Rails for API-only Applications
*Menggunakan Rails hanya untuk aplikasi API saja*

In this guide you will learn:

* What Rails provides for API-only applications
*Apa yang Rails sediakan untuk aplikasi API.*

* How to configure Rails to start without any browser features
*Bagaimana cara konfigurasi Rails untuk start tanpa fitur browser*

* How to decide which middleware you will want to include
*Bagaimana menentukan middleware yang ingin anda gunakan*

* How to decide which modules to use in your controller
*Bagaimana cara menentukan module mana yang ingin anda gunakan pada controller anda*


## 1. What is an API Application?

Traditionally, when people said that they used Rails as an "API", they meant providing a programmatically accessible API alongside their web application. For example, GitHub provides an API that you can use from your own custom clients. 
*Secara sederhana, ketika orang berkata mereka menggunakan Rails sebagai "API", yang mereka maksud adalah mereka menyediakan pemrograman API yang bisa diakses bersama dengan aplikasi web mereka*

With the advent of client-side frameworks, more developers are using Rails to build a back-end that is shared between their web application and other native applications.
*Dengan munculnya klien side framework, banyak developer menggunakan Rails untuk membangun back-end yang terbagi antara web aplikasi dan aplikasi native lainnya*

For example, Twitter uses its public API in its web application, which is built as a static site that consumes JSON resources.
*Contoh, Twitter menggunakan public API pada web aplikasinya, yg mana dibangun sebagai statis website yang mengkonsumsi JSON resources.*

Instead of using Rails to generate HTML that communicates with the server through forms and links, many developers are treating their web application as just an API client delivered as HTML with JavaScript that consumes a JSON API.
*Berbeda dengan menggunakan Rails to men-generate HTML yang berkomunikasi dengan server melalui forms dan link, banyak pengembang yang memperlakukan aplikasi web mereka hanya sebagai klien API disampaikan sebagai HTML dengan JavaScript yang mengkonsumsi JSON API.*

This guide covers building a Rails application that serves JSON resources to an API client, including client-side frameworks.
*Panduan ini mencakup membangun aplikasi Rails yang melayani sumber JSON ke klien API, termasuk client-side framework.*

## 2. Why Use Rails for JSON APIs?

The first question a lot of people have when thinking about building a JSON API using Rails is: "isn't using Rails to spit out some JSON overkill? Shouldn't I just use something like Sinatra?".
*Pertanyaan pertama banyak orang berfikir tentang membangun sebuah API JSON menggunakan Rails adalah: "bukankah menggunakan Rails untuk menghasilkan JSON itu membuang waktu? bukankah saya lebih baik menggunakan semacam Sinatra?".*

For very simple APIs, this may be true. However, even in very HTML-heavy applications, most of an application's logic lives outside of the view layer.
*Untuk API sederhana, ini mungkin benar. Akan tetapi, meski dalam aplikasi HTML yang berat, kebanyakan sebuah logik aplikasi berada di luar view layer*

The reason most people use Rails is that it provides a set of defaults that allows developers to get up and running quickly, without having to make a lot of trivial decisions.
*Alasan orang kebanyakan menggunakan Rails adalah karena telah disedikannya pengaturan standar yang mengijinkan pengembang untuk bisa memulai dengan cepat, tanpa harus mengeluarkan keputusan yang kurang berarti*

Let's take a look at some of the things that Rails provides out of the box that are still applicable to API applications.
*Marilah kita melihat beberapa hal dimana Rails menyediakan (out of the box) yang masih bisa digunakan untuk aplikasi API*

#### Handled at the middleware layer:

*Ditangani pada lapisan middleware*

* Reloading: Rails applications support transparent reloading. This works even if your application gets big and restarting the server for every request becomes non-viable.
*Reloading: Aplikasi Rails mendukung reload transparansi. Ini akan bekerja bahkan jika aplikasi Anda menjadi besar dan restart server setiap mendapat request (request becomes non-viable) yang menjadi tidak-layak.*

* Development Mode: Rails applications come with smart defaults for development, making development pleasant without compromising production-time performance.
*Development Mode: Aplikasi Rails datang dengan pengaturan cerdas untuk pengembangan, membuat pengembangan menjadi nyaman tanpa mengorbankan kinerja waktu-produksi*

* Test Mode: Ditto development mode.

* Logging: Rails applications log every request, with a level of verbosity appropriate for the current mode. Rails logs in development include information about the request environment, database queries, and basic performance information.
*Logging: Aplikasi Rails mencatat / log setiap request, dengan tinggkat penggunakaan kata yang tepat untuk mode yang bersangkutan. Rails logs pada development menyertakan informasi tentang lingkungan permintaan, database queries dan basic performance informasi.*

* Security: Rails detects and thwarts IP spoofing attacks and handles cryptographic signatures in a timing attack aware way. Don't know what an IP spoofing attack or a timing attack is? Exactly.
*Sekuriti: Rails mendeteksi dan menggagalkan IP serangan jahat dan menangani cryptographic signatures dengan cara menyadari waktu serangan. Tidak mengetahui serangan jahat IP atau waktu serangan? Tentu saja*

* Parameter Parsing: Want to specify your parameters as JSON instead of as a URL-encoded String? No problem. Rails will decode the JSON for you and make it available in params. Want to use nested URL-encoded parameters? That works too.
*Parameter Parsing: Apakah ingin menspesifikasi parameters sebagai JSON bukan sebagai URL-encoded String? Tidak masalah. Rails akan decode JSON dan membuat tersedia dalam params. Ingin menggunakan nested URL-encoded paramenters? Ini juga bisa*

* Conditional GETs: Rails handles conditional GET (ETag and Last-Modified) processing request headers and returning the correct response headers and status code. All you need to do is use the stale? check in your controller, and Rails will handle all of the HTTP details for you.
*Kondisional GETs: Rails menangani kondisional GET (ETag and Last-Modified) memproses request header dan mengembalikan dengan benar respon header dan status kode. Semua yang anda butuh lakukan adalah menggunakan (hal) membosankan / basi (stale)? Cek kedalam controller anda dan Rails akan menangani semua detil HTTP untuk anda* 

* HEAD requests: Rails will transparently convert HEAD requests into GET ones, and return just the headers on the way out. This makes HEAD work reliably in all Rails APIs.
*Head requests: Rails akan transparan dalam mengkonversi HEAD request ke dalam suatu GET dan mengembalikannya sama seperti keluaran headers. Ini membuat HEAD bekerja dengan baik dalam semua Rails APIs.*

While you could obviously build these up in terms of existing Rack middleware, this list demonstrates that the default Rails middleware stack provides a lot of value, even if you're "just generating JSON".
*Meski anda dapat membangun ini dalam hal Rack middleware, lis ini menunjukan bahwa secara default Rails middleware stack menyediakan banyak value, meskipun anda "hanya generate JSON".*

**Handled at the Action Pack layer**:
*Menangani pada Lapisan Action Pack*

* Resourceful Routing: If you're building a RESTful JSON API, you want to be using the Rails router. Clean and conventional mapping from HTTP to controllers means not having to spend time thinking about how to model your API in terms of HTTP.
*Resourceful Routing: Jika anda membangun sebuah RESTful JSON API, anda ingin menggunakan Rails router, Bersih dan convensional Mapping dari HTTP ke controllers artinya tidak menghabiskan waktu berfikir tentang bagaimana membuat model API anda dalam hal HTTP.*

* URL Generation: The flip side of routing is URL generation. A good API based on HTTP includes URLs (see the GitHub Gist API for an example).
*URL Generation: Sisi lain dari routing adalah generasi URL. Sebuah basis API pada HTTP termasuk URLs (lihat [Github Gist API](https://developer.github.com/v3/gists/) sebagai contoh)*

* Header and Redirection Responses: head :no_content and redirect_to user_url(current_user) come in handy. Sure, you could manually add the response headers, but why?
*Header and Redirection Responses: head :no_content and redirect_to user_url(current_user) dilakukan dengan mudah. Pasti, anda dapat lakukan dengan manual menambahkan response headers, tapi kenapa?*

* Caching: Rails provides page, action and fragment caching. Fragment caching is especially helpful when building up a nested JSON object.
*Caching: Rails menyediakan halaman, action dan fragment caching. Fragment caching adalah terutama sangat membantu ketika membangun sebuah nested JSON object.*

* Basic, Digest, and Token Authentication: Rails comes with out-of-the-box support for three kinds of HTTP authentication.
*Basic, Digest, and Token Authentication: Rails datang dengan out-of-the-box support untuk 3 hal dari HTTP authentication.*

* Instrumentation: Rails has an instrumentation API that triggers registered handlers for a variety of events, such as action processing, sending a file or data, redirection, and database queries. The payload of each event comes with relevant information (for the action processing event, the payload includes the controller, action, parameters, request format, request method and the request's full path).
*Instrumentation: Rails memiliki instrumen API yang men-triger registered handler untuk beberapa event, seperti action processing, mengirim file atau data, redirection dan database queries. Payload dari masing-masing event datang dengan informasi yang relevan (untuk action processing event, payload termasuk controller, action, parameters, request format, request method dan request full path )*

* Generators: It is often handy to generate a resource and get your model, controller, test stubs, and routes created for you in a single command for further tweaking. Same for migrations and others.
*Generators: Adalah sering dengan mudah untuk generate sebuah resource dan get model, controller, test stubs, dan create route untuk anda dalam single perintah untuk tweaking lebih lanjut. Sama seperti migration dan lainnya.*

* Plugins: Many third-party libraries come with support for Rails that reduce or eliminate the cost of setting up and gluing together the library and the web framework. This includes things like overriding default generators, adding Rake tasks, and honoring Rails choices (like the logger and cache back-end).
*Plugins: Banyak libraries pihak ke tiga datang dengan dukungan untuk Rails yang mengurangi dan membatasi waktu setup dan merekat bersama antara library dan web framework. Ini termasuk hal-hal seperti overriding default generator, menambahkan Rake tasks, dan menjunjung pilihan Rails (seperti logger dan cache back-end)*

Of course, the Rails boot process also glues together all registered components. For example, the Rails boot process is what uses your config/database.yml file when configuring Active Record.
*Tentunya, boot proses Rails juga melekat bersama semua registered komponen. Contoh, Rails boot proses adalah apa yang anda gunakan pada file config/database.yml ketika mengkonfigurasi Active Record.*

**The short version is:** you may not have thought about which parts of Rails are still applicable even if you remove the view layer, but the answer turns out to be most of it.
*The short version is: Secara singkat mungkin anda berfikir tentang bagian mana dari Rails yang masih aplikabel even jika anda me remove view layer, tapi jawabannya ternyata lebih banyak dari itu. *

## 3. The Basic Configuration

If you're building a Rails application that will be an API server first and foremost, you can start with a more limited subset of Rails and add in features as needed.
*Jika anda membangun sebuah aplikasi Rails yang akan menjadi API server pertama dan terpenting, adalah anda bisa mulai dengan batasan subset dari Rails dan menambahkannya pada fitur saat membutuhkannya.*

### 3.1 Creating a new application

You can generate a new api Rails app:

	$ rails new my_api --api  # my local: sites_api$

This will do three main things for you:

* Configure your application to start with a more limited set of middleware than normal. Specifically, it will not include any middleware primarily useful for browser applications (like cookies support) by default.

* Make ApplicationController inherit from ActionController::API instead of ActionController::Base. As with middleware, this will leave out any Action Controller modules that provide functionalities primarily used by browser applications.

* Configure the generators to skip generating views, helpers and assets when you generate a new resource.

### 3.2 Changing an existing application

If you want to take an existing application and make it an API one, read the following steps.

In config/application.rb add the following line at the top of the Application class definition:

	config.api_only = true

* In config/environments/development.rb, set/add :
	
	config.debug_exception_response_format 

to configure the format used in responses when errors occur in development mode.

* To render an HTML page with debugging information, use the value :default.

	config.debug_exception_response_format = :default

* To render debugging information preserving the response format, use the value :api.

	config.debug_exception_response_format = :api

By default, config.debug_exception_response_format is set to :api, when config.api_only is set to true.

Finally, inside app/controllers/application_controller.rb, instead of:	

	class ApplicationController < ActionController::Base
	end

do

	class ApplicationController < ActionController::API
	end	

## 4. Choosing Middleware

An API application comes with the following middleware by default:

+ Rack::Sendfile
+ ActionDispatch::Static
+ ActionDispatch::Executor
+ ActiveSupport::Cache::Strategy::LocalCache::Middleware
+ Rack::Runtime
+ ActionDispatch::RequestId
+ Rails::Rack::Logger
+ ActionDispatch::ShowExceptions
+ ActionDispatch::DebugExceptions
+ ActionDispatch::RemoteIp
+ ActionDispatch::Reloader
+ ActionDispatch::Callbacks
+ ActiveRecord::Migration::CheckPending
+ Rack::Head
+ Rack::ConditionalGet
+ Rack::ETag	

See [the internal middleware](http://edgeguides.rubyonrails.org/rails_on_rack.html#internal-middleware-stack) section of the Rack guide for further information on them.

Other plugins, including Active Record, may add additional middleware. In general, these middleware are agnostic to the type of application you are building, and make sense in an API-only Rails application.

You can get a list of all middleware in your application via:

	$ rails middleware

### 4.1 Using the Cache Middleware

By default, Rails will add a middleware that provides a cache store based on the configuration of your application (memcache by default). This means that the built-in HTTP cache will rely on it.

For instance, using the stale? method:

	def show
	  @post = Post.find(params[:id])
	 
	  if stale?(last_modified: @post.updated_at)
	    render json: @post
	  end
	end

The call to stale? will compare the If-Modified-Since header in the request with @post.updated_at. If the header is newer than the last modified, this action will return a "304 Not Modified" response. Otherwise, it will render the response and include a Last-Modified header in it.

Normally, this mechanism is used on a per-client basis. The cache middleware allows us to share this caching mechanism across clients. We can enable cross-client caching in the call to stale?:

	def show
	  @post = Post.find(params[:id])
	 
	  if stale?(last_modified: @post.updated_at, public: true)
	    render json: @post
	  end
	end

This means that the cache middleware will store off the Last-Modified value for a URL in the Rails cache, and add an If-Modified-Since header to any subsequent inbound requests for the same URL.

Think of it as page caching using HTTP semantics.	

## 4.2 Using Rack::Sendfile

When you use the send_file method inside a Rails controller, it sets the X-Sendfile header. Rack::Sendfile is responsible for actually sending the file.

If your front-end server supports accelerated file sending, Rack::Sendfile will offload the actual file sending work to the front-end server.

You can configure the name of the header that your front-end server uses for this purpose using config.action_dispatch.x_sendfile_header in the appropriate environment's configuration file.

You can learn more about how to use Rack::Sendfile with popular front-ends in the Rack::Sendfile documentation.

Here are some values for this header for some popular servers, once these servers are configured to support accelerated file sending:

# Apache and lighttpd
	
	config.action_dispatch.x_sendfile_header = "X-Sendfile"
 
# Nginx
	
	config.action_dispatch.x_sendfile_header = "X-Accel-Redirect"

Make sure to configure your server to support these options following the instructions in the Rack::Sendfile documentation.

### 4.3 Using ActionDispatch::Request

ActionDispatch::Request#params will take parameters from the client in the JSON format and make them available in your controller inside params.

To use this, your client will need to make a request with JSON-encoded parameters and specify the Content-Type as application/json.

Here's an example in jQuery:	

	jQuery.ajax({
	  type: 'POST',
	  url: '/people',
	  dataType: 'json',
	  contentType: 'application/json',
	  data: JSON.stringify({ person: { firstName: "Yehuda", lastName: "Katz" } }),
	  success: function(json) { }
	});

	ActionDispatch::Request will see the Content-Type and your parameters will be:

		{ :person => { :firstName => "Yehuda", :lastName => "Katz" } }

### 4.4 Other Middleware

Rails ships with a number of other middleware that you might want to use in an API application, especially if one of your API clients is the browser:

Rack::MethodOverride
ActionDispatch::Cookies
ActionDispatch::Flash
For session management
ActionDispatch::Session::CacheStore
ActionDispatch::Session::CookieStore
ActionDispatch::Session::MemCacheStore
Any of these middleware can be added via:		