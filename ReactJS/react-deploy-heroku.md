# React Deployment Heroku

### The Steps

	heroku login (Enter your Heroku credentials)
	
	git init
	
	git add .
	
	git commit -m “initial commit”
	
	heroku create (You should see two links after running this command. Copy the second one)
	
	git remote add heroku PASTE THE LINK YOU JUST COPIED
	
	git push heroku master


### Error 1

	remote:  !     No default language could be detected for this app.
	remote: 			HINT: This occurs when Heroku cannot detect the buildpack to use for this application automatically.
	remote: 			See https://devcenter.heroku.com/articles/buildpacks
	remote: 
	remote:  !     Push failed
	remote: Verifying deploy...
	remote: 
	remote: !	Push rejected to sleepy-basin-77168.
	remote: 
	To https://git.heroku.com/sleepy-basin-77168.git
	 ! [remote rejected] master -> master (pre-receive hook declined)
	error: failed to push some refs to 'https://git.heroku.com/sleepy-basin-77168.git'

#### Solusi 1

Biasanya error ini terjadi karena anda belum meLakukan git init, so lakukan ```git init```:

	git init
	
### Error	2

	remote: -----> Build failed
	remote:  !     Two different lockfiles found: package-lock.json and yarn.lock
	remote: 
	remote:        Both npm and yarn have created lockfiles for this application,
	remote:        but only one can be used to install dependencies. Installing
	remote:        dependencies using the wrong package manager can result in missing
	remote:        packages or subtle bugs in production.
	remote: 
	remote:        - To use npm to install your application's dependencies please delete
	remote:          the yarn.lock file.
	remote: 
	remote:          $ git rm yarn.lock
	remote: 
	remote:        - To use yarn to install your application's dependences please delete
	remote:          the package-lock.json file.
	remote: 
	remote:          $ git rm package-lock.json
	remote:  

#### Solusi 2

Jika di laptop anda terinstal yarn maka akan di generate 2 buah file **lock**, Hapus salah satu nya:

	git rm yarn.lock
	
atau

	git rm package-lock.json
	
	
Jangan lupa lakukan lagi dibawah ini:

	git add .
	git commit dan 
	heroku push master lagi.
	
dan bila tidak ada lagi error, lakukan:
	
	heroku open
	
<br>	
	
### Merubah Nama app

contoh menjadi: https://reactwebsite-project.herokuapp.com/

Bila merubah di web heroku kemudian lakukan ini di CLI:

	git remote rm heroku
	heroku git:remote -a newname	
	
newname: reactwebsite-project

done :)