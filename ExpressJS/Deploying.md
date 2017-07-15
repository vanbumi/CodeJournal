# Deploy to Digitalocean

## Install forever

**On server !**

	sudo apt-get install npm

	sudo npm install -g forever

Add deploy user
[Learncodeacademy-gist](https://gist.github.com/learncodeacademy/3cdb928c9314f98404d0)

Copy and paste this command:

	sudo useradd --create-home -s /bin/bash deploy
	sudo adduser deploy sudo
	sudo passwd deploy

in this case I still using my own user (dyo)

**On local !**

Install **flightplan**

	sudo npm install -g flightplan

In my project folder 

	npm install flightplan --save-dev	 

or 

	npm install --save-dev fly

I used first one

Just test type fly, it will

	Error: flightplan.js not found

So create file flightplan.js

	touch flightplan.js

can not continue waiting for staging information.		 