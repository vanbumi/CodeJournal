## Node connected to mongodb atlas

**Install Mongoose**

```
npm install mongoose
```

**String Connection**

```javascript
// app.js

const mongoose = require('mongoose');

const MongoClient = require('mongodb').MongoClient;
const uri = "mongodb+srv://dyo:dyo123@airlineroleapi-s142s.mongodb.net/test?retryWrites=true&w=majority";
const client = new MongoClient(uri, { 
    useNewUrlParser: true, 
    useUnifiedTopology: true
});
client.connect(err => {
  const collection = client.db("test").collection("devices");
  // perform actions on the collection object
  client.close();
  console.log('Connected to database mongodb atlas');
});
```