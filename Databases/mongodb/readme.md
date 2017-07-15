# MongoDB

To run mongo from terminal, type
	
	$ mongod --dbpath ~/data/db
    
Open new tab terminal, type:

	$ mongo  

MongoDB will run as bellow:

	dyo@dyo-medio:~/codejournal$ mongo
	MongoDB shell version: 2.6.11
	connecting to: test
	Server has startup warnings: 
	2016-02-17T11:18:08.263+0700 [initandlisten] 
	2016-02-17T11:18:08.263+0700 [initandlisten] ** NOTE: This is a 32 bit MongoDB binary.
	2016-02-17T11:18:08.263+0700 [initandlisten] **       32 bit builds are limited to less than 2GB of data (or less with --journal).
	2016-02-17T11:18:08.263+0700 [initandlisten] **       Note that journaling defaults to off for 32 bit and is currently off.
	2016-02-17T11:18:08.263+0700 [initandlisten] **       See http://dochub.mongodb.org/core/32bit
	2016-02-17T11:18:08.263+0700 [initandlisten] 
	>

Sample mongodb commands:

	2016-02-17T11:18:08.263+0700 [initandlisten] 
	> use mean-demo
	switched to db mean-demo
	> show collections
	> db.meetups.insert({ name: "Dyo Stack Developer" })
	WriteResult({ "nInserted" : 1 })
	> show collections
	meetups
	system.indexes
	> db.meetups.find()
	{ "_id" : ObjectId("56c3f4ef918123e9d96ff191"), "name" : "Dyo Stack Developer" }
	> 

Add more documents:

	> db.meetups.insert({ name: "Dyo Stack Developer", speaker: "Radio Bodol" })
	WriteResult({ "nInserted" : 1 })
	> db.meetups.find()
	{ "_id" : ObjectId("56c3f4ef918123e9d96ff191"), "name" : "Dyo Stack Developer" }
	{ "_id" : ObjectId("56c3f6d1918123e9d96ff192"), "name" : "Dyo Stack Developer", "speaker" : "Radio Bodol" }
	> 

MongoDB in terminal command

	dyo@dyo-medio:~$ mongo
	MongoDB shell version: 2.6.11
	connecting to: test
	Server has startup warnings: 
	2016-02-18T23:32:16.567+0700 [initandlisten] 
	2016-02-18T23:32:16.567+0700 [initandlisten] ** NOTE: This is a 32 bit MongoDB binary.
	2016-02-18T23:32:16.567+0700 [initandlisten] **       32 bit builds are limited to less than 2GB of data (or less with --journal).
	2016-02-18T23:32:16.567+0700 [initandlisten] **       Note that journaling defaults to off for 32 bit and is currently off.
	2016-02-18T23:32:16.567+0700 [initandlisten] **       See http://dochub.mongodb.org/core/32bit
	2016-02-18T23:32:16.567+0700 [initandlisten] 
	> show dbs
	admin      (empty)
	local      0.078GB
	mean-demo  0.078GB
	> use contactlist
	switched to db contactlist
	> db.contactlist.insert({name: 'Tom', email: 'tom@email.com', number: '(444) 444-4444'})
	WriteResult({ "nInserted" : 1 })
	> db.contactlist.find()
	{ "_id" : ObjectId("56c5f35c5efae4ea30c1642d"), "name" : "Tom", "email" : "tom@email.com", "number" : "(444) 444-4444" }
	> db.contactlist.find().pretty()
	{
		"_id" : ObjectId("56c5f35c5efae4ea30c1642d"),
		"name" : "Tom",
		"email" : "tom@email.com",
		"number" : "(444) 444-4444"
	}
	> db.contactlist.insert([{name: 'Tracy', email: 'tracy@email.com', number: '(555) 555-5555'}, {name: 'Tucker', email: 'tucker@testmail.com', number: '(777) 777-7777'}])
	BulkWriteResult({
		"writeErrors" : [ ],
		"writeConcernErrors" : [ ],
		"nInserted" : 2,
		"nUpserted" : 0,
		"nMatched" : 0,
		"nModified" : 0,
		"nRemoved" : 0,
		"upserted" : [ ]
	})
	> db.contactlist.find().pretty()
	{
		"_id" : ObjectId("56c5f35c5efae4ea30c1642d"),
		"name" : "Tom",
		"email" : "tom@email.com",
		"number" : "(444) 444-4444"
	}
	{
		"_id" : ObjectId("56c5f7145efae4ea30c1642e"),
		"name" : "Tracy",
		"email" : "tracy@email.com",
		"number" : "(555) 555-5555"
	}
	{
		"_id" : ObjectId("56c5f7145efae4ea30c1642f"),
		"name" : "Tucker",
		"email" : "tucker@testmail.com",
		"number" : "(777) 777-7777"
	}
	> 
