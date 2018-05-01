## All error I found and Solution anywhere

MongoError: E11000 duplicate key error index: mongoosecobafsd.users.$email_1 dup key: { : null }

  The error message is saying that there's already a record with null as the email. In other words, you already have a user without an email address.
  https://stackoverflow.com/questions/24430220/e11000-duplicate-key-error-index-in-mongodb-mongoose

MongoError: Authentication failed. at Function.MongoError.create 