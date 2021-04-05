## Python MongoDB Connectivity
To create connection between Python programming language and MongoDB database, we need to first install pymongo driver. Here, we are creating an example that connects to the database and performs basic database operations.

This example includes the following steps:

1) Install Driver

       pip install pymongo 

2) python codes

```python
    from pymongo import MongoClient # import mongo client to connect  

    # Creating instance of mongoclient  
    client = MongoClient()  

    # Creating database  
    db = client.javatpoint  
    employee = {"id": "101",  
            "name": "Peter",  
            "profession": "Software Engineer",  
            } 

    # Creating document  
    employees = db.employees  

    # Inserting data  
    employees.insert_one(employee)  

    # Fetching data  
    print(employees.find_one())  
```
