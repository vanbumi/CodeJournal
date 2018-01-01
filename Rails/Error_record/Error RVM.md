## Case learnetto React Rails

> .rvm/rubies/ruby-2.3.3/lib/ruby/site_ruby/2.3.0/rubygems/core_ext/kernel_require.rb:55:in `require': cannot load such file -- rails/cli (LoadError)

Solution:

You have installed rvm but forget to install rails gem. Install it use:

    gem install rails

    bundle install

and last

    rails s

> Your Ruby version is 2.4.0, but your Gemfile specified 2.3.3

    rvm install 2.3.3
    rvm use 2.3.3

> Can't find appointments.js in /home/dyo/sites/latihan/calreact/public/packs/manifest.json. Is webpack still compiling?

    RAILS_ENV=production bundle exec rake assets:precompile

not work? try add this to gemfile:

    gem 'webpacker', github: "rails/webpacker"

followed by 

    bundle install 
    
and 
    
    bin/rake webpacker:install 
    
Install Yarn

No solve!

    Webpacker can't find appointments.js in /home/dyo/sites/latihan/calreact/public/packs/manifest.json. Possible causes:
    1. You want to set webpacker.yml value of compile to true for your environment
    unless you are using the `webpack -w` or the webpack-dev-server.
    2. Webpack has not yet re-run to reflect updates.
    3. You have misconfigured Webpacker's config/webpacker.yml file.
    4. Your Webpack configuration is not creating a manifest.
    Your manifest contains:
    {
    }
    Extracted source (around line #7):
    5
    6
    7
    8
                
    #appointments_data{data: @appointments.to_json}

    = javascript_pack_tag 'appointments'
    = stylesheet_pack_tag 'appointments'





