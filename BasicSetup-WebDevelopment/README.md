Basic Setup Ruby on Rails Website On Digital Ocean Server
=========================================================

Before action it might good references :)
    https://medium.com/@rkukuh/kumpulan-resource-untuk-web-developer-februari-2016-143ec0e4dc9d#.aeevkzrn6

STEPS
-----
1. LOCAL > CREATE APP
---------------------
    rails new appname -d mysql or -d postgresql
    
2. REMOTE > CREATE BARE REPOSITORY
----------------------------------
    > access ssh
    > cd repo
    > git init --bare --shared reponame.git
    
3. LOCAL > DO GIT INIT 
----------------------
    git init
    git status
    git ignored > ignore /config/database.yml
    git add .
    git commit
    git push github or push to private server
        
4. LOCAL > ADD GIT REMOTE
-------------------------
    example : $ git remote add deploy dyo@widyobumi.com:/home/dyo/repo/reponame.git
    
5. LOCAL > GIT PUSH
------------------- 
    $ git push deploy master

    
6. REMOTE > GIT CLONE
---------------------
    $ cd to/sites
    example : the_site$ git clone dyo@widyobumi.com:/home/dyo/repo/repname.git 

Apache Server
-------------
    
>> For Apache2 server SETUP continue here https://www.digitalocean.com/community/tutorials/how-to-deploy-a-rails-app-with-passenger-and-apache-on-ubuntu-14-04

we need to create a virtual host file for our project. We'll do this by copying the default Apache virtual host:

    sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/nameapp.conf

Open the config file

    sudo nano /etc/apache2/sites-available/testapp.conf

Edit it or replace the existing contents so your final result matches the file shown below. Changes you need to make are highlighted in red. Remember to use your own domain name, and the correct path to your Rails app:

    <VirtualHost *:80>
        *ServerName example.com
        *ServerAlias www.example.com
        ServerAdmin webmaster@localhost
        DocumentRoot /home/rails/testapp/public
        *RailsEnv development
        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
        *<Directory "/home/rails/testapp/public">
            Options FollowSymLinks
            Require all granted
        </Directory>
    </VirtualHost>    

Disable the default site, enable your new site, and restart Apache:

    sudo a2dissite 000-default
    sudo a2ensite testapp
    sudo service apache2 restart        
    

7. SETUP sites-available for NGINX Server 
-----------------------------------------
    > cd /etc/nginx/sites-available
    > mkdir sitename.conf
    > and write as bellow:
    
        server {
        server_name codemedio.tk;
        passenger_enabled on;
        passenger_app_env development;
        root /home/dyo/sites/codemedio/public;
        }   
    
8. CREATE SYMLINK
-----------------
Create a symlink for that above:

    $ sudo ln -s /etc/nginx/sites-available/codemedio /etc/nginx/sites-enabled/codemedio
    
Restart Nginx:

    sudo nginx -s reload or
    sudo service nginx restart
 
9. REMOTE > SETUP DOMAIN @ DOMAIN HOST
--------------------------------------
    ref: https://www.digitalocean.com/community/tutorials/how-to-set-up-a-host-name-with-digitalocean
        
10. SETUP NAME SERVER di DOMAIN SERVER
--------------------------------------
    ns1.digitalocean.com
    ns2.digitalocean.com
    ns3.digitalocean.com    
            
11. REMOTE > ADD Domain @ DIGITIAL OCEAN
----------------------------------------        

12. REMOTE > SETUP the DATABASE
-------------------------------

13. REMOTE > RUN bundle install
-------------------------------

14. REMOTE > rake db:create
---------------------------

15. REMOTE > rake db:migrate
----------------------------

## Incase If you find Errors:
   
#### Error #1

    Web application could not be started
    Could not find a JavaScript runtime. See https://github.com/rails/execjs for a list of available runtimes. (ExecJS::RuntimeUnavailable)

solution:

    go to activate >> gem 'therubyracer', platforms: :ruby

    $ bundle install
                        
#### Error #2

    There was an error while trying to load the gem 'uglifier'. (Bundler::GemRequireError)
    /usr/local/lib/ruby/gems/2.3.0/gems/bundler-1.11.2/lib/bundler/runtime.rb:80:in `rescue in block (2 levels) in  require'

solution:   

    go to activate >> gem 'therubyracer', platforms: :ruby

Another error: There was an error while trying to load the gem 'uglifier'. (Bundler::GemRequireError)

Solution:

    sudo apt-get install nodejs    
                        
#### Error #3

    PG::InvalidParameterValue: ERROR:  new encoding (UTF8) is incompatible with the encoding of the template database (SQL_ASCII)
    HINT:  Use the same encoding as in the template database, or use template0 as template.
                      
Solution: https://gist.github.com/amolkhanorkar/8706915

    Steps resolved the problem:

    * First, we need to drop template1. Templates can’t be dropped, so we first modify it so t’s an ordinary database:

        UPDATE pg_database SET datistemplate = FALSE WHERE datname = 'template1';

    * Now we can drop it:

        DROP DATABASE template1;

    * Now its time to create database from template0, with a new default encoding:

        CREATE DATABASE template1 WITH TEMPLATE = template0 ENCODING = 'UNICODE';

    * Now modify template1 so it’s actually a template:

        UPDATE pg_database SET datistemplate = TRUE WHERE datname = 'template1';

    * Now switch to template1 and VACUUM FREEZE the template:

        \c template1

        VACUUM FREEZE;

Problem should be resolved :)
      
  
#### Error #4

    Gem::LoadError: You have already activated rake 10.5.0, but your Gemfile requires rake 10.4.2. Prepending `bundle exec` to your command may solve this.

Solution:

    sudo bundle exec rake db:create

    sudo bundle exec rake db:migrate

    


                        
                        
                        