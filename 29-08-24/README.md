**Create commands:**  

1.db.col_name.insertOne({})

2.db.col_name.insertMany([{}]}: Array of objects

3.db.col_name.insertOne({date:ISODate()}):Inbuilt gives current date

4.db.col_name.find(): to show all documents in a collection.

5.db.col_name.find().pretty():in a orgainsed format

**Read command:**

db.col_name.findOne() : find out the specific one document

Example 1 : **By using ID** db.User.findOne({_id: ObjectId('66cebdd72fb98ab7642710c2')})

Output: 

{
_id: ObjectId('66cebdd72fb98ab7642710c2'),
name: 'Charlie',
age: 27,
marks: 85,
subject: 'Chemistry'
}

Example 2: **By using Name**  db.User.findOne({name:'leen'})

Output: 

{
_id: ObjectId('66cebaf82fb98ab7642710bc'),
name: 'leen',
age: 19,
class: 'g9'
}

**Note: If you create two documents by same name the first one will show (the first created)**

Hw: explore commands of CREATE operation











Command Prompt:

Microsoft Windows [Version 10.0.22631.4037]
(c) Microsoft Corporation. All rights reserved.

C:\Users\kharl>mongosh
Current Mongosh Log ID: 66cff5ea882ffe0ecd2710bb
Connecting to:          mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.3.0
Using MongoDB:          7.0.14
Using Mongosh:          2.3.0

For mongosh info see: https://www.mongodb.com/docs/mongodb-shell/

------
   The server generated these startup warnings when booting
   2024-08-28T10:04:08.871+05:30: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted
------

test> use newdb
switched to db newdb
newdb> show collections
dbcollect
Faculty
User
newdb> db.User.insertOne({date:ISODate()})
{
  acknowledged: true,
  insertedId: ObjectId('66cff830882ffe0ecd2710bc')
}
newdb> db.User.find()
[
  {
    _id: ObjectId('66cebaf82fb98ab7642710bc'),
    name: 'leen',
    age: 19,
    class: 'g9'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c0'),
    name: 'Alice',
    age: 25,
    marks: 88,
    subject: 'Mathematics'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c1'),
    name: 'Bob',
    age: 22,
    marks: 91,
    subject: 'Physics'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c2'),
    name: 'Charlie',
    age: 27,
    marks: 85,
    subject: 'Chemistry'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c3'),
    name: 'Diana',
    age: 24,
    marks: 92,
    subject: 'Biology'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c4'),
    name: 'Edward',
    age: 26,
    marks: 79,
    subject: 'Computer Science'
  },
  {
    _id: ObjectId('66cff830882ffe0ecd2710bc'),
    date: ISODate('2024-08-29T04:25:20.739Z')
  }
]
newdb> db.User.find().pretty()
[
  {
    _id: ObjectId('66cebaf82fb98ab7642710bc'),
    name: 'leen',
    age: 19,
    class: 'g9'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c0'),
    name: 'Alice',
    age: 25,
    marks: 88,
    subject: 'Mathematics'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c1'),
    name: 'Bob',
    age: 22,
    marks: 91,
    subject: 'Physics'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c2'),
    name: 'Charlie',
    age: 27,
    marks: 85,
    subject: 'Chemistry'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c3'),
    name: 'Diana',
    age: 24,
    marks: 92,
    subject: 'Biology'
  },
  {
    _id: ObjectId('66cebdd72fb98ab7642710c4'),
    name: 'Edward',
    age: 26,
    marks: 79,
    subject: 'Computer Science'
  },
  {
    _id: ObjectId('66cff830882ffe0ecd2710bc'),
    date: ISODate('2024-08-29T04:25:20.739Z')
  }
]
newdb> db.User.findOne()
{
  _id: ObjectId('66cebaf82fb98ab7642710bc'),
  name: 'leen',
  age: 19,
  class: 'g9'
}


newdb> db.User.findOne({_id: ObjectId('66cebdd72fb98ab7642710c2')})
{
  _id: ObjectId('66cebdd72fb98ab7642710c2'),
  name: 'Charlie',
  age: 27,
  marks: 85,
  subject: 'Chemistry'
}
newdb> db.User.findOne({name:'leen'})
{
  _id: ObjectId('66cebaf82fb98ab7642710bc'),
  name: 'leen',
  age: 19,
  class: 'g9'
}
newdb> db.User.insertOne({name:'leen',age:20,class:'g8'})
{
  acknowledged: true,
  insertedId: ObjectId('66cffe51882ffe0ecd2710bd')
}
newdb> db.User.findOne({name:'leen'})
{
  _id: ObjectId('66cebaf82fb98ab7642710bc'),
  name: 'leen',
  age: 19,
  class: 'g9'
}
