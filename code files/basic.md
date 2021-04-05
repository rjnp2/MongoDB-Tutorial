## MongoDB Create Database
  Syntax:
  use firstdb  
  
  To check the database list, use the command show dbs:
  show dbs  
  
## MongoDB Drop Database
  Syntax:
  db.dropDatabase() 
  
## MongoDB Create Collection
  Syntax:
  db.createCollection("firstcol")  

## MongoDB Drop collection
  Syntax:
  db.firstcol.drop()
  
## MongoDB insert documents
   Syntax:
   db.firstcol.insert(  
  {  
...      course: "java",  
...      details: {  
...         duration: "6 months",  
...         Trainer: "Sonoo jaiswal"  
...      },  
...      Batch: [ { size: "Small", qty: 15 }, { size: "Medium", qty: 25 } ],  
...      category: "Programming language"  
...    }  
... ) 

