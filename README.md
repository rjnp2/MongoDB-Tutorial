# NoSQL Databases
[Python MongoDB](https://github.com/rjnp2/MongoDB-Tutorial/blob/main/Python%20MongoDB.ipynb)

We know that MongoDB is a NoSQL Database, so it is very necessary to know about NoSQL Database to understand MongoDB throughly.

NoSQL Database is used to refer a non-SQL or non relational database.

It provides a mechanism for storage and retrieval of data other than tabular relations model used in relational databases. NoSQL database doesn't use tables for storing data. It is generally used to store big data and real-time web applications.

Advantages of NoSQL 

    It supports query language.
    It provides fast performance.
    It provides horizontal scalability.
___

# What is MongoDB
MongoDB is an open-source document database that provides high performance, high availability, and automatic scaling. In simple words, you can say that - Mongo DB is a document-oriented database.

Our MongoDB tutorial includes all topics of MongoDB database such as insert documents, update documents, delete documents, query documents, projection, sort() and limit() methods, create a collection, drop collection, etc. There are also given MongoDB interview questions to help you better understand the MongoDB database.

It also supports: JSON data model with dynamic schemas, Auto-sharding for horizontal scalability, Built in replication for high availability.
 
## MongoDB Datatypes

Data Types |	Description
|--|--|
String |	String is the most commonly used datatype. It is used to store data. A string must be UTF 8 valid in mongodb.
Integer |	Integer is used to store the numeric value. It can be 32 bit or 64 bit depending on the server you are using.
Boolean |	This datatype is used to store boolean values. It just shows YES/NO values.
Double |	Double datatype stores floating point values.
Min/Max Keys |	This datatype compare a value against the lowest and highest bson elements.
Arrays |	This datatype is used to store a list or multiple values into a single key.
Object |	Object datatype is used for embedded documents.
Null |	It is used to store null values.
Symbol |It is generally used for languages that use a specific type.
Date |	This datatype stores the current date or time in unix time format. It makes you possible to specify your own date time by creating object of date and pass the value of date, month, year into it.

## How to install MongoDB on Linux
  sudo apt-get install mongodb
  
  mongodb
  
## MongoDB Create Database
  Syntax:
  
      use DATABASE_NAME  
  
  To check the database list, use the command show dbs:
  
        show dbs  
  
## MongoDB Drop Database
  Syntax:
  
        db.dropDatabase()  
  
## MongoDB Create Collection
  Syntax:
        
        db.createCollection(name, options)   
  Here, Name: is a string type, specifies the name of the collection to be created.
        Options: is a document type, specifies the memory size and indexing of the collection. It is an optional parameter.
        
        show collections  

## MongoDB Drop collection
  Syntax:
        
        db.COLLECTION_NAME.drop()  
  
## MongoDB insert documents
   Syntax
        
        db.COLLECTION_NAME.insert(document)  
   
## MongoDB insert multiple documents
       
       var Allcourses =  [ {}, {},  ]
       db.COLLECTION_NAME.insert( Allcourses );
   
## Check the inserted documents
  If the insertion is successful, you can view the inserted document by the following query.
  Syntax:
        
        db.COLLECTION_NAME.find()  

## Insert multiple documents with Bulk
In its latest version of MongoDB (MongoDB 2.6) provides a Bulk() API that can be used to perform multiple write operations in bulk.
You should follow these steps to insert a group of documents into a MongoDB collection.
Initialize a bulk operation builder

  Syntax:    

    var bulk = db.javatpoint.initializeUnorderedBulkOp(); 
   This operation returns an unorder operations builder which maintains a list of operations to perform .

Add insert operations to the bulk object \
  Syntax:    

    bulk.insert( { } );    
Execute the bulk operation
Call the execute() method on the bulk object to execute the operations in the list.

    bulk.execute();  
  
## MongoDB update documents
  Syntax:

        db.COLLECTION_NAME.update(SELECTIOIN_CRITERIA, UPDATED_DATA)  
   example: db.COLLECTION_NAME.update({'course':'java'},{$set:{'course':'android'}})
   
## MongoDB Delete documents
In MongoDB, the db.colloction.remove() method is used to delete documents from a collection. The remove() method works on two parameters.
Deletion criteria: With the use of its syntax you can remove the documents from the collection, JustOne: It removes only one document when set to true or 1. \
    Syntax:

        db.collection_name.remove (DELETION_CRITERIA) 
    Remove all documents
        db.javatpoint.remove({})   
    Remove all documents that match a condition
         db.javatpoint.remove( { type : "programming language" } )  
    Remove a single document that match a condition
          db.javatpoint.remove( { type : "programming language" }, 1 )  

## MongoDB Query documents
In MongoDB, the db.collection.find() method is used to retrieve documents from a collection. This method returns a cursor to the retrieved documents. \
    Syntax:

        db.COLLECTION_NAME.find({}) 
        
    Select all documents in a collection:
    To retrieve all documents from a collection, put the query document ({}) empty. It will be like this:
        db.COLLECTION_NAME.find()   
        
## Create and Alter commands
SQL statements	| MongoDB statements
|--|--|
CREATE TABLE JavaTpoint () | db.createCollection ( " JavaTpoint " )
DROP TABLE people | db.people.drop ()

## MongoDB and SQL Insert Statement
SQL Insert statement |	MongoDB insert statement
|--|--|
INSERT INTO JavaTpoint () VALUES () | db.JavaTpoint.insert({ })

## SQL and Mongo DB Select Command
SQL SELECT Statement |	MongoDB find() Statement
|--|--|
SELECT * FROM JavaTpoint | db.JavaTpoint.find()
SELECT id, user_id, status FROM JavaTpoint | db.JavaTpoint.find( { }, { user_id: 1, status: 1 } )
SELECT user_id, status FROM JavaTpoint | db.JavaTpoint.find( { }, { user_id: 1, status: 1, _id: 0 } )
SELECT * FROM JavaTpoint WHERE status = "B" | db.JavaTpoint.find( { status: "A" } )
SELECT * FROM JavaTpoint WHERE status = "A" AND age = 50 | db.JavaTpoint.find({ status: "A", age: 50 } )
SELECT * FROM JavaTpoint WHERE status = "A" OR age = 50 | db.JavaTpoint.find( { $or: [ { status: "A" } , { age: 50 } ] })
SELECT * FROM JavaTpoint WHERE age > 25 | db.JavaTpoint.find({ age: { $gt: 25 } })
SELECT * FROM JavaTpoint WHERE user_id like "%bc%" | db.JavaTpoint.find( { user_id: /bc/ } )
SELECT * FROM JavaTpoint WHERE user_id like "bc%" | db.JavaTpoint.find( { user_id: /^bc/ } )
SELECT * FROM JavaTPoint WHERE status = "A" ORDER BY user_id ASC | db. JavaTPoint. find( { status: "A" } ). sort( { user_id: 1 } )
SELECT COUNT(user_id) FROM JavaTPoint | db. JavaTPoint.count( { user_id: { $exists: true } } )
SELECT COUNT(*) FROM JavaTPoint WHERE age > 30 | db. JavaTPoint.count( { age: { $gt: 30 } } )
SELECT DISTINCT(status) FROM JavaTPoint | db. JavaTPoint.aggregate( [ { $group : { _id : "$status" } } ] ) or db. JavaTPoint.distinct( "status" )
SELECT * FROM JavaTPoint LIMIT 1 | db. JavaTPoint.findOne() or db. JavaTPoint.find(). limit(1)
SELECT * FROM JavaTPoint LIMIT 5 SKIP 10 | db. JavaTPoint.find(). limit(5). skip(10)
EXPLAIN SELECT * FROM JavaTPoint WHERE status = "A" | db. JavaTPoint. find( { status: "A" } ). explain()

## SQL and MongoDB Update Statements
SQL Update Statements | MongoDB updateMany() Statements
|--|--|
UPDATE JavaTpoint SET status = "C" WHERE age > 25 | db.JavaTpoint.updateMany( { age: { $gt: 25 } }, { $set: { status: "C" } } )
UPDATE JavaTpoint SET age = age + 3 WHERE status = "A" | db.JavaTpoint.updateMany( { status: "A" } , { $inc: { age: 3 } } )

## SQL and MongoDB Delete Statements

SQL Delete Statements	| MongoDB deleteMany() Statements
|--|--|
DELETE FROM JavaTpoint WHERE status = "D" | db.JavaTpoint.deleteMany( { status: "D" } )
DELETE FROM JavaTpoint | db.JavaTpoint.deleteMany( { } )

