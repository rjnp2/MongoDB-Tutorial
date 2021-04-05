## MongoDB text search
MongoDB performs a text search of string content using the query operation. It uses a text index and operator to perform the text search.

Example:
It shows you "how to build a text index and use it to find your books".

Now, you have to create a collection named "library" as follows:

    db.library.insert(  
       [  
         { _id: 101, name: "Java", description: "By ABC" },  
         { _id: 102, name: "MongoDB", description: "By XYZ" },  
         { _id: 103, name: "Python", description: "By ABCD" },  
         { _id: 104, name: "Engineering Mathematics", description: "By *****" },  
         { _id: 105, name: "Salesforce", description: "By Salesforce" }  
       ]  
    )  
    
   ![1](https://github.com/rjnp2/MongoDB-Tutorial/blob/main/images/1.png)

##  Text Index
In MongoDB we have text indexes to support text search queries on string content. The field that have any string value or an array of string elements may include by text indexes

We must have a text index in our collection to perform text search queries. In a table/collection, we can have only one text search index. But multiple fields can be covered by a single index.

We can run the following example in Mongo shell to allow text search cover the name and description fields:

    db.library.createIndex( { name: "text", description: "text" } )  
![1](https://github.com/rjnp2/MongoDB-Tutorial/blob/main/images/2.png)

## $text Operator
We can use the $text operator to perform text searches on a table with a text index. The $text operator will flag the search string which uses the whitespaces and also most of the punctuation as delimiters. The $text operator performs a logical OR operation for all such tokens in the search string.

In the below example, we can use the query to find all libraries containing any books name related to "MongoDB", "Java", "DBMS", etc.

    db.library.find( { $text: { $search: "Java" } } )

Using the $text operator, we can also search for exact phrases by wrapping them in double-quotes. Only those documents will be matched that include the phrases.

For Example -

    db.library.find( { $text: { $search: "\"Java Book\"" } } )  

![1](https://github.com/rjnp2/MongoDB-Tutorial/blob/main/images/3.png)

## Sorting
MongoDB return the result by default in unsorted order. An optimum score will be computed for each document by the text search query that specifies how well a document matches the query.

    db.library.find(  
       { $text: { $search: "java" } },  
       { score: { $meta: "textScore" } }  
    ).sort( { score: { $meta: "textScore" } } )  

![1](https://github.com/rjnp2/MongoDB-Tutorial/blob/main/images/4.png)
