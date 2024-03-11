# Learning MongoDB.  
#### MongoDB is a source-available, cross-platform, document-oriented database program. Classified as a NoSQL database product, MongoDB utilizes JSON-like documents with optional schemas. MongoDB is developed by MongoDB Inc. and current versions are licensed under the Server Side Public License.  


<p align="center">
<img src="image-1.png" />
<p/>


### Basic commands for MongoDB Shell.
1. To show Databases -
```
> show dbs
```

2. To use/connect to a Database OR to make new Databse -
```
> use database-name
```

3. To make new collection  -
```
> db.createCollection("collection-name")
```

4. To drop a Database (you need to be in that database) -
```
> use school
> db.dropDatabase()
    //deletes current database
```

5. Inserting document in a database. In MongoDB we save data by inserting documents in the collection. Same as key:value pairs in JSON -
```
> use school
    //using database school.

> db.createCollection("students")
    //creating new collection named students.

> db.students.insertOne({name:'Spongebob', age:30, gpa:3.2})
    //inserting one document into the collection.
```

6. To show contents of a collection.
```
> db.students.find()

//multiple fiters
> db.students.find({gpa:4.0, fullTime:true})
```

7. Projection.

```
//syntax
> db.students.find({-filter-}, {-projection-})


//examples
> db.students.find({fullTime:true}, {name:true, _id:false})

> db.students.find({}, {name:true, gpa:true, _id:false})
``` 

8. Sorting and limiting.  
```
//syntax
> db.-collectionName-.find().sort({-field- : -ascending(1) and decending(-1)-})

> db.-collectionName-.find().limit(-limitNumber-)



//examples
> db.students.find().sort({name:1})
    //this will sort the outputs by name and ascending order

> db.students.find().limit(2)
    //this will limit results to 2

//both sorting and limiting
> db.students.find().sort({gpa:1}).limit(5)
```

9. Update fields.
```
//update one
//syntax
> db.students.updateOne({-selection criteria-}, {$set:{-update field:value-}})


//examples
>db.students.updateOne({name:'Spongebob'}, {$set:{fullTime:true}})


//update many
//syntax
> db.students.updateMany({-selection criteria-}, {$set:{-update field:value-}})

//examples
//$exists checks if does the document has that field.
> db.students.updateMany({fullTime:{$exits:false}}, {$set:{fullTime:true}})
```