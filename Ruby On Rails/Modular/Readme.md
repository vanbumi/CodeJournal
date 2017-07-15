# Steps

* Clone
* Add coba.text
* git add .
* git commit
* git push origin master
* Setup preparation

## Preparation

Before start, make sure you already run all this step below.

Create User inside Database

### Create DB User

CREATE USER "mesin-user";
ALTER USER "mesin-user" WITH LOGIN;
ALTER USER "mesin-user" WITH PASSWORD 'mesin-user';
ALTER USER "mesin-user" WITH SUPERUSER;
Setup environment variables

Move into mesin-apps directory and then setup .env file like this:

export DEV_DB_USER='mesin-user'
export DEV_DB_PASS='mesin-user

* titik titik