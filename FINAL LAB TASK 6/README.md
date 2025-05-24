# Final Lab Task 6: MongoDB Practice
For this task, we are given initial query in order to used and develop hands-on skills in managing and querying data using MongoDB.

## Here’s the Query Statements

First, select the database you want to work with in MongoDB.
use mongo_practice
### Create Database

![Sample Output](images/FIRST.PNG)

### Insert Documents

![Sample Output](images/DOCS1.PNG)

![Sample Output](images/DOCS2.PNG)

### Query Find
db.movies.find()
![Sample Output](images/FIND1.PNG)

![Sample Output](images/FIND2.PNG)

db.movies.find({writer:”Quentin Tarantino”})
![Sample Output](images/QUENTIN.PNG)

db.movies.find({actors:”Brad Pitt”})
![Sample Output](images/BRADD.PNG)

db.movies.find({franchise:”The Hobbit”})
![Sample Output](images/HOBBIT.PNG)

db.movies.find({year:{$gt:”1990”, $lt:”2000”}})
![Sample Output](images/2000.PNG)

db.movies.find({$or:[{year:{$gt:”2010”}},{year: {$lt:”2000”}}]})
![Sample Output](images/2010.PNG)

### Update Documents

db.movies.update({_id:ObjectId("5c9f98e5e5c2dfe9b3729bfe")}, {$set:{synopsis:"A reluctant hobbit, Bilbo Baggins, sets out to the Lonely Mountain with a spirited group of dwarves to reclaim their mountain home - and the gold within it - from the dragon Smaug."}})
db.movies.update({_id:ObjectId("5c9fa42ae5c2dfe9b3729c03")}, {$set:{synopsis:"The dwarves, along with Bilbo Baggins and Gandalf the Grey, continue their quest to reclaim Erebor, their homeland, from Smaug. Bilbo Baggins is in possession of a mysterious and magical ring."}})
db.movies.update({_id:ObjectId("5c9f983ce5c2dfe9b3729bfc")}, {$push:{actors:"Samuel L. Jackson"}})
![Sample Output](images/UPDATE.PNG)

### Text Search

db.movies.find({synopsis:{$regex:"Bilbo"}})
db.movies.find({synopsis:{$regex:"Gandalf"}})
db.movies.find({$and:[{synopsis:{$regex:"Bilbo"}}, {synopsis:{$not:/Gandalf/}}]})
db.movies.find({$or:[{synopsis:{$regex:"dwarves"}}, {synopsis:{$regex:"hobbit"}}]})
db.movies.find({$and:[{synopsis:{$regex:"gold"}}, {synopsis:{$regex:"dragon"}}]})
![Sample Output](images/SEARCH.PNG)

### Delete Documents

db.movies.remove({_id:ObjectId("5c9f992ae5c2dfe9b3729c00")})
db.movies.remove({_id:ObjectId("5c9f9936e5c2dfe9b3729c01")})
![Sample Output](images/DELETE.PNG)
