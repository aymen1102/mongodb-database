1 - Build Docker compose : `docker-compose up -d`<br/>

There is two ways to connect to DB:Display only the totalSpentInBooks :<br/>
first method :<br/>
2 - Run the mongo express GUI client with this URL : `http://localhost:8081/` <br/>
second method :<br/>
3 - Go inside the mongo container : `docker exec -it <CONTAINER_ID> bash` <br/>
4 - Connect to the database using mongo shell : ` mongo mongodb://localhost:27017 -u rootuser -p rootpass`<br/>
5 - Show database list with this command :  `show dbs;`<br/>
6 - Create a new database : `use database_name;`<br/>
7 - Get the database name : `db.getName();`<br/>
8 - Show database list with this command :  `show dbs;`<br/>
9 - Create a collection : `db.createCollection("person");`<br/>
10- Show collections list with this command :  `show collections;`<br/>
11- Show a collection parameters :  `db.person.stats()`<br/>
12- Delete collection : `db.person.drop()` <br/>
13- Delete a database :  `db.dropDatabase();` <br/>
14- Get all commands :  `db.help();` <br/>
15- Create a collection with parameters : `db.createCollection("person",{capped:true,size:9142800, max: 3000})` <br/>

Mango stores documents (rows) in collections (table) <br/>
16- Copy Paste the object student on the cmd <br/>
17- Create the collection student : `db.createCollection(student)` <br/>
18- Insert a document in the collection : `db.student.insert(student)` <br/>
19- Copy Paste the object students on the cmd <br/>
20- Insert a document in the collection : `db.student.insertMany(students)` <br/>
21- Get documents number : `db.student.count()` <br/>
22- Display indented students documents : `db.student.find().pretty()` <br/>
23- Display the whole document student with a firstName Zidane : `db.student.find({firstName:'Zinedine'}).pretty()` <br/>
24- Display the firstName only : `db.student.find({firstName:'Zinedine'},{firstName:1}).pretty()` <br/>
25- Display only the firstName and the lastName : `db.student.find({firstName:'Zinedine'},{firstName:1, lastName:1}).pretty()` <br/>
26- Display all document without the firstName and the lastName : `db.student.find({firstName:'Zinedine'},{firstName:0,lastName:0}).pretty()` <br/>
27- Display all firstName, lastName documents : `db.student.find({},{firstName:1,lastName:1}).pretty()` <br/>
28- Display all firstName, lastName, gender documents : `db.student.find({},{firstName:1,lastName:1,gender:1}).pretty()` <br/>
29- Update the firstName with document identified with id : `db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$set:{firstName:'Maria'}})` <br/>
30- get all the document without the lastName of the document identified with id : `db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$unset:{lastName:1}})` <br/>
31- Display only the totalSpentInBooks : `db.student.find({},{totalSpentInBooks:1}).pretty()` <br/>
32- Increment the totalSpentInBooks with 15 :`db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$inc:{totalSpentInBooks:15}})` <br/>
33- Display only the totalSpentInBooks : `db.student.find({},{totalSpentInBooks:1}).pretty()` <br/>
34- Delete it subject from the document : `db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$pull:{favouriteSubjects:'it'}})` <br/>
35- Display only the totalSpentInBooks : `db.student.find({},{favouriteSubjects:1}).pretty()` <br/>
36- Add it subject to the document`db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$push:{favouriteSubjects:'it'}})` <br/>
37- Display all documents ids : `db.student.find({},{_id:1}).pretty()` <br/>
38- Delete document with id :  `db.student.deleteOne({_id:ObjectId("622604db24c73a122897cd8b")})` <br/>
39- Delete the last document `db.student.deleteOne({})` <br/>
40- Delete all documents : `db.student.deleteMany({})` <br/>