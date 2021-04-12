## All error I found and Solution anywhere

MongoError: E11000 duplicate key error index: mongoosecobafsd.users.$email_1 dup key: { : null }

  The error message is saying that there's already a record with null as the email. In other words, you already have a user without an email address.
  https://stackoverflow.com/questions/24430220/e11000-duplicate-key-error-index-in-mongodb-mongoose

MongoError: Authentication failed. at Function.MongoError.create 



> Error: listen EADDRINUSE: address already in use port

Solution:

```
ps aux | grep node

You'll see a listing similar to this:

davidwalsh       12413   0.0  0.0  2592088   3888   ??  S     7:38PM   0:20.45 /Users/davidwalsh/Projects/debugger.html/node_modules/flow-bin/flow-osx-v0.52.0/flow
davidwalsh       12412   0.0  0.0 29739356   2372   ??  S     7:38PM   0:00.12 /Users/davidwalsh/Projects/debugger.html/node_modules/flow-bin/flow-osx-v0.52.0/flow
davidwalsh       12411   0.0  0.0 29732188   2372   ??  S     7:38PM   0:00.07 /Users/davidwalsh/Projects/debugger.html/node_modules/flow-bin/flow-osx-v0.52.0/flow
davidwalsh       12410   0.0  0.0 29732188   2372   ??  S     7:38PM   0:00.07 /Users/davidwalsh/Projects/debugger.html/node_modules/flow-bin/flow-osx-v0.52.0/flow
davidwalsh       12409   0.0  0.0 29731164   2372   ??  S     7:38PM   0:00.06 /Users/davidwalsh/Projects/debugger.html/node_modules/flow-bin/flow-osx-v0.52.0/flow
When you identify the rogue process, use the kill command along with the process number to remove it:

#kill -9 {process_number}
kill -9 12413

With the process killed you can now start up the server as normal!
```

