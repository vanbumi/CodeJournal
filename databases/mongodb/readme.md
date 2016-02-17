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

