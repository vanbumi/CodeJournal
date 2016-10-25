## Error !

rake aborted! Multiple migrations have the name CreateFavorites

	If you type "git status" it should show the inconsistency. It will say something like this:

	# On branch master
	# Changed but not updated:
	#   (use "git add/rm <file>..." to update what will be committed)
	#   (use "git checkout -- <file>..." to discard changes in working directory)
	#
	#       deleted:    db/migrate/20101007030431_create_favorites.rb
	So just follow the instructions there. To permanently remove it from the repository, type:

	git rm db/migrate/20101007030431_create_favorites.rb

[Stack Overflow](http://stackoverflow.com/questions/4017571/removing-duplicate-db-migrations-from-git-repository)	