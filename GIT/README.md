# GIT

## [Git Tutorial](https://git-scm.com/docs/gittutorial)

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


## References	

[Git Is Simpler Than You Think](http://nfarina.com/post/9868516270/git-is-simpler)

## Branching

Check Branch

	git branch

Add branch

	git branch new_branch

Switch to new_branch

	git checkout new_branch

## Merge Branch

	git checkout master

	git merge new_branch

## Remove Branch

	git branch -d branch_to_remove

If found error, do following command: 

error: The branch 'devel-revise-1' is not fully merged. If you are sure you want to delete it, run '

	git branch -D devel-revise-1

## Revise recent commit

	git commit --amend -m "New commit message"

## Go back to my commit in past

	git checkout e4af64a77

Message:

	Note: checking out 'e4af64a77'.

	You are in 'detached HEAD' state. You can look around, make experimental changes and commit them, and you can discard any commits you make in this state without impacting any branches by performing another checkout.

	If you want to create a new branch to retain commits you create, you may do so (now or later) by using: -b with the checkout command again. Example:

		git checkout -b <new-branch-name>

	HEAD is now at e4af64a... finish v.142 Successfull save to Firebase 	
		
My experimentals :

I do checkout another commit after above commit:

	git checkout 4cb5d52022ea

I am making any changes, commit it and create new branch named devel-revise-1 and I will merge it into branch devel-revise.

## Back to last work fine commit and remove all commit since that.

I follow this steps:

* Create new branch eq: devel-revise

* State of devel and devel-revise branch is similar state.

* In devel-revise checkout the last work fine commit.

* In this commit state create new branch: devel-fine.

* remove devel-revise

* git checkout devel-fine

* Now you work with devel-fine ready to merge to master if some case.

* **Case** I have master mess up, and branch can_upload better one, I want to change can_upload to become master:

**solution:**

	git checkout better_branch
	git merge --strategy=ours master   # keep the content of this branch, but record a merge
	git checkout master
	git merge better_branch             # fast-forward master up to the merge

if error : Error reading /home/dyo/.nano_history: Permission denied

use sudo git merge --strategy=ours master	

https://stackoverflow.com/questions/2763006/make-the-current-git-branch-a-master-branch


