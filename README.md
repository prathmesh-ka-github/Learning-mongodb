# Learning MongoDB.  

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
```

5. Inserting document in a database. In MongoDB we save data by inserting documents in the collection. Same as key:value pairs in JSON -
```
> use school
\\using database school.

> db.createCollection("students")
\\creating new collection named students.

> db.students.insertOne({name:'Spongebob', age:30, gpa:3.2})
\\inserting one document into the collection.
```

6. To show contents of a collection.
```
> db.students.find()
```

7. Sorting 