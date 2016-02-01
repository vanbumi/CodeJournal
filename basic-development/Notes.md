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
    > mkdir reponame
    > cd reponame
    > git init --bare --shared reponame.git
    
3. LOCAL > DO GIT INIT 
----------------------
    git init
    git status
    git ignored > ignore /config/database.yml
    git add .
    git commit
    git push github
        
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
    
>> For Apache2 server SETUP continue here https://www.digitalocean.com/community/tutorials/how-to-deploy-a-rails-app-with-passenger-and-apache-on-ubuntu-14-04
    
7. SETUP sites-available 
------------------------
    > cd /etc/nginx/sites-available/namesites
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
            
11. REMOTE > ADD DOMAIN @ DIGITIAL OCEAN
----------------------------------------        

12. REMOTE > SETUP DATABASE NYA
-------------------------------

13. REMOTE > RUN BUNDLE INSTALL
-------------------------------

14. REMOTE > RAKE DB:CREATE
---------------------------

15. REMOTE > RAKE DB:MIGRATE
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
      
  
                        
                        
                        
                        