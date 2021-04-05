# NoSQL Databases
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




  
 
