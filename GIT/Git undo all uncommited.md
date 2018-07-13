## git undo all uncommitted or unsaved changes

This will unstage all files you might have staged with git add:

* git reset
This will revert all local uncommitted changes (should be executed in repo root):

* git checkout .
You can also revert uncommitted changes only to particular file or directory:

* git checkout [some_dir|file.txt]
Yet another way to revert all uncommitted changes (longer to type, but works from any subdirectory):

* git reset --hard HEAD
This will remove all local untracked files, so only git tracked files remain:

* git clean -fdx

**WARNING**: -x will also remove all ignored files, including ones specified by .gitignore! You may want to use -n for preview of files to be deleted.

To sum it up: executing commands below is basically equivalent to fresh git clone from original source (but it does not re-download anything, so is much faster):

	git reset
	git checkout .
	git clean -fdx

Typical usage for this would be in build scripts, when you must make sure that your tree is absolutely clean - does not have any modifications or locally created object files or build artefacts, and you want to make it work very fast and to not re-clone whole repository every single time.

https://stackoverflow.com/questions/14075581/git-undo-all-uncommitted-or-unsaved-changes

