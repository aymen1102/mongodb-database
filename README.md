1 - Build Docker compose : `docker-compose up -d`<br/>

There is two ways to connect to DB:
first method :
2 - Run the mongo express GUI client with this URL : `http://localhost:8081/`
second method :
3 - Go inside the mongo container : `docker exec -it <CONTAINER_ID> bash` <br/>
4 - Connect to the database using mongo shell : ` mongo mongodb://localhost:27017 -u rootuser -p rootpass`<br/>
5 - Show database list with this command :  `show dbs;`
6 - Create a new database : `use database_name;`
7 - Get the database name : `db.getName();`
8 - Show database list with this command :  `show dbs;`
9 - Create a collection : `db.createCollection("person");`
10- Show collections list with this command :  `show collections;`
11- Show a collection parameters :  `db.person.stats()`
12- Delete collection : `db.person.drop()`
13- Delete a database :  `db.dropDatabase();`
14- Get all commands :  `db.help();`
15- Create a collection with parameters : `db.createCollection("person",{capped:true,size:9142800, max: 3000})`

Mango stores documents (rows) in collections (table)
16- Copy Paste the object student on the cmd
17- Create the collection student : `db.createCollection(student)`
18- Insert a document in the collection : `db.student.insert(student)`
19- Copy Paste the object students on the cmd
20- Insert a document in the collection : `db.student.insertMany(students)`
21- Get documents number : `db.student.count()`
22- Display indented students documents : `db.student.find().pretty()`
23- Display the whole doument student with a firstName Zidane : `db.student.find({firstName:'Zinedine'}).pretty()`
24- Display the firstName only : `db.student.find({firstName:'Zinedine'},{firstName:1}).pretty()`
25- Display only the firstName and the lastName : `db.student.find({firstName:'Zinedine'},{firstName:1, lastName:1}).pretty()`
26- Display all document without the firstName and the lastName  `db.student.find({firstName:'Zinedine'},{firstName:0,lastName:0}).pretty()`
27- `db.student.find({},{firstName:1,lastName:1}).pretty()`
28- `db.student.find({},{firstName:1,lastName:1,gender:1}).pretty()`
29- `db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$set:{firstName:'Maria'}})`
30- `db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$unset:{lastName:1}})`
31- Display only the totalSpentInBooks : `db.student.find({},{totalSpentInBooks:1}).pretty()`
32- `db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$inc:{totalSpentInBooks:15}})`
33- Display only the totalSpentInBooks : `db.student.find({},{totalSpentInBooks:1}).pretty()`
34- `db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$pull:{favouriteSubjects:'it'}})`
35- Display only the totalSpentInBooks : `db.student.find({},{favouriteSubjects:1}).pretty()`
36- `db.student.update({_id: ObjectId("622604db24c73a122897cd8b")},{$push:{favouriteSubjects:'it'}})`
37- `db.student.find({},{_id:1}).pretty()`
38- Delete document with id :  `db.student.deleteOne({_id:ObjectId("622604db24c73a122897cd8b")})`
39- `db.student.deleteOne({})`
40- `db.student.deleteMany({})`