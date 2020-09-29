# DAT250: Software Technology Experiment Assignment 3

### Technical problems that you encountered during installation and use of MongoDB and how you resolved
No technical problems that I encountered during the completion of the tutorial.

### Screenshots for:
- The correct validation of the installation package (https://docs.mongodb.com/manual/tutorial/verify-mongodb-packages/):  
Validating the MongoDB installation package using SHA-256 checksum  
![SSValidation](screenshots/Screenshot-validation.png)

- Relevant results obtained during Experiment 1 (it is not necessary to put a single screenshot on each substep, but at least one significant from each CRUD operation):  
    - Insert (here: Multiple):
    ![insert](screenshots/Screenshot-insertM.png)
    - Query (here: AND condition):
    ![query](screenshots/Screenshot-queryAND.png)
    - Update (here: a single document):
    ![Update](screenshots/Screenshot-update.png)
    - Delete (here: Only One Document that Matches a Condition):
    ![Delete](screenshots/Screenshot-deleteOne.png)
    - BulkWrite() (here: performs multiple operations on the collection):
    ![BulkWrite](screenshots/Screenshot-bulkWrite.png)
    
[//]: # (hei er dette en kommentar??????)

- Experiment 2 example working and the additional Map-reduce operation (and its result) developed by each of you:  
    - Aggregation:  
    ![aggregation](screenshots/Screenshot-aggregation.png)
    - Additional operation developed by me using the same db as prev (Here: Total number of times per customer):  
    ![aggregationME](screenshots/Screenshot-aggregationEM.png)



### Reason about why your implemented Map-reduce operation in Experiment 2 is useful and interpret the collection obtained.
My implemented Map-reduced operation in Experiment 2 is useful for times when you want to know how many times the same `cust_id` has appeared in the database. The results gives us: 
```
{ "_id" : "Ant O. Knee", "value" : 2 }
{ "_id" : "Busby Bee", "value" : 3 }
{ "_id" : "Cam Elot", "value" : 2 }
{ "_id" : "Don Quis", "value" : 3 }
```
Which says that "Ant O. Knee" appeared 2 times, "Busby Bee" 3 times, "Cam Elot" 2 times and "Don Quis" 3 times.

### Any pending issues with this assignment which you did not manage to solve
No pending issues with this assignment which I did not manage to solve.
