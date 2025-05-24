# Final Lab Task 6: MongoDB Practice
For this task, we are given initial query in order to used and develop hands-on skills in managing and querying data using MongoDB.

## Here’s the Query Statements

First, select the database you want to work with in MongoDB.
```sql
use mongo_practice
```
### Create Database

![Sample Output](images/1.png)

### Insert Documents

![Sample Output](images/2.PNG)

![Sample Output](images/3.PNG)

![Sample Output](images/4.PNG)

### Query Find
```sql

db.movies.find()

![Sample Output](images/find.1.PNG)

![Sample Output](images/find.2.PNG)

![Sample Output](images/find.3.PNG)

db.movies.find({writer:”Quentin Tarantino”})
![Sample Output](images/quentin.png)

![Sample Output](images/quentin2.png)

db.movies.find({actors:”Brad Pitt”})
![Sample Output](images/bradd.png)

![Sample Output](images/bradd2.png)


db.movies.find({franchise:”The Hobbit”})
![Sample Output](images/hobbit.png)

db.movies.find({year:{$gt:”1990”, $lt:”2000”}})
![Sample Output](images/1990.png)

db.movies.find({$or:[{year:{$gt:”2010”}},{year: {$lt:”2000”}}]})
![Sample Output](images/2010.png)

![Sample Output](images/2010.1.png)

![Sample Output](images/2010.2.png)


```
### Update Documents
```sql
db.movies.update({_id:ObjectId("5c9f98e5e5c2dfe9b3729bfe")}, {$set:{synopsis:"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}})
db.movies.update({_id:ObjectId("5c9fa42ae5c2dfe9b3729c03")}, {$set:{synopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
db.movies.update({_id:ObjectId("5c9f983ce5c2dfe9b3729bfc")}, {$push:{actors:"Samuel L. Jackson"}})
![Sample Output](images/update.PNG)
```
### Text Search
```sql
db.movies.find({synopsis:{$regex:"Bilbo"}})
db.movies.find({synopsis:{$regex:"Gandalf"}})
db.movies.find({$and:[{synopsis:{$regex:"Bilbo"}}, {synopsis:{$not:/Gandalf/}}]})
db.movies.find({$or:[{synopsis:{$regex:"dwarves"}}, {synopsis:{$regex:"hobbit"}}]})
db.movies.find({$and:[{synopsis:{$regex:"gold"}}, {synopsis:{$regex:"dragon"}}]})
![Sample Output](images/SEARCH.PNG)
```
### Delete Documents
```sql
db.movies.remove({_id:ObjectId("5c9f992ae5c2dfe9b3729c00")})
db.movies.remove({_id:ObjectId("5c9f9936e5c2dfe9b3729c01")})
![Sample Output](images/remove.PNG)
```
