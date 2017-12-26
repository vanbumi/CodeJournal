**rake aborted! Errno::EACCES: Permission denied @ rb_sysopen**

#### Solutions

down vote
Check the permissions for your db directory, it seems your user does not have write permission for it.

Make sure the entire app directory and its subfolders belong to your user:

  chown -R `whoami` /home/u/eol

And add the write permission to all folders:

  chmod -R u+w /home/u/eol