# GIT

## Revert Git repo to a previous commit

* [Stack Overflow](http://stackoverflow.com/questions/4114095/revert-git-repo-to-a-previous-commit)
* [Rollback to an old Git commit in a public repo](http://stackoverflow.com/questions/2007662/rollback-to-an-old-git-commit-in-a-public-repo)

### Git Cache

To untrack a single file that has already been added/initialized to your repository, i.e., stop tracking the file but not delete it from your system use: 

	git rm --cached filename

To untrack every file that is now in your .gitignore:

First commit any outstanding code changes, and then, run this command:

	git rm -r --cached .

This removes any changed files from the index(staging area), then just run:

	git add .

Commit it:

	git commit -m ".gitignore is now working"

To undo 

	git rm --cached filename, use git add filename.

