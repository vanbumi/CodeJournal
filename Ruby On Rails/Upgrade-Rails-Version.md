# How to Upgrade Ruby and Rails Version

## Check the Gem Manager

RubyGems is the gem manager in Ruby.

Check the installed gem manager version:

    $ gem -v

Newer RubyGems version is here [rubygems-update](https://rubygems.org/gems/rubygems-update). Use **gem update --system** to upgrade the Ruby gem manager:

    $ gem update --system

## RVM Gemsets

RVM gives you gemsets, which are sandboxed environments that let you maintain separate sets of gems. Gemsets are ideal for multiple versions of Rails.

Display a list of gemsets:

    dyo@ubuntu:~$ rvm gemset list

    gemsets for ruby-2.4.0 (found in /home/xxx/.rvm/gems/ruby-2.4.0)
    => (default)
    global
    rails5.1.3

Only the “default” and “global” gemsets are pre-installed.

*If you get an error “rvm is not a function,” close your console and open it again.*

## RVM’s Global Gemset

See what gems are installed in the “global” gemset:

**A trouble-free** development environment requires the newest versions of the default gems.

    $ rvm gemset use global
    -> Using ruby-2.4.0 with gemset global

    $ gem list
    -> bigdecimal (default: 1.3.0)
    bundler-unload (1.0.2)
    did_you_mean (1.1.0)
    executable-hooks (1.3.2)
    ...

### To get a list of gems that are outdated:

    $ gem outdated

### To update all stale gems:

    $ gem update

Ttrack updates to gems at the ```RubyGems.org``` create an account and visit your [**dashboard**](https://rubygems.org/dashboard). Search for each gem you use and “subscribe” to see a feed of updates in the dashboard (an RSS feed is available from the dashboard). Alternative, use the [**Gemnasium**](https://gemnasium.com/) service which surveys your GitHub repo and sends email notifications when gem versions change. **Gemnasium is free for public repositories** with a premium plan for private repositories.

## Nokogiri

[Nokogiri](http://www.nokogiri.org/) is a gem that is a dependency for many other gems (specifically, the rails-html-sanitizer gem and its dependency, the loofah gem). Nokogiri is a gem that requires compilation for your specific operating system. As such, if your system environment doesn’t match Nokogiri’s requirements, compilation of Nokogiri will fail. If your system is configured properly, you’ll be able to compile Nokogiri. However, compilation takes time. Every time you install the Nokogiri gem, you’ll wait (as long as five minutes).

To save time, install the Nokogiri gem in the RVM global gemset:

    $ gem install nokogiri

During installation, Nokogiri will display two lengthy messages in the console. It will also pause without displaying any progress for as long as five minutes. Don’t assume installation has failed unless you see an error message or you’ve waited more than ten minutes.

If installation fails, make sure your system is configured properly (look for help on Stack Overflow).

## Simple Rails Update

**Gemfile** specifies Rails version is used. If you have a Rails 4.2.4 will show below: 

    source 'https://rubygems.org'
    gem 'rails', '4.2.4'

You can change the Rails version to a newer version of Rails. For example, update it to Rails 4.2.5:

    source 'https://rubygems.org'
    gem 'rails', '4.2.5'

**Then run**:

    $ bundle update rails
    $ rails -v
        

Continue: http://railsapps.github.io/updating-rails.html




