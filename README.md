Got it — you want proper Markdown with code blocks (```) so GitHub renders it correctly. Here’s the complete raw README.md ready to copy:


---

# Next Generation Database Lab (MongoDB)

Name: Tanuj Narula  
Course: AIDS-A  

Start MongoDB shell:
```bash
mongosh

Create / Switch Database:

use mydb

Show Databases:

show dbs

Show Current Database:

db

Drop Database:

db.dropDatabase()

Create Collection:

db.createCollection("students")

Show Collections:

show collections

Create Collection with Options:

db.createCollection("col6", {
  capped: true,
  autoIndexId: true,
  size: 5000,
  max: 10000
})

Drop Collection:

db.col5.drop()

Insert One:

db.posts.insertOne({
  title: "Post Title 1",
  body: "Body of post.",
  category: "News",
  likes: 1,
  tags: ["news", "events"],
  date: Date()
})

Insert Many:

db.posts.insertMany([
  {
    title: "Post Title 2",
    body: "Body of post.",
    category: "Event",
    likes: 2,
    tags: ["news", "events"],
    date: Date()
  },
  {
    title: "Post Title 3",
    body: "Body of post.",
    category: "Technology",
    likes: 3,
    tags: ["news", "events"],
    date: Date()
  },
  {
    title: "Post Title 4",
    body: "Body of post.",
    category: "Event",
    likes: 4,
    tags: ["news", "events"],
    date: Date()
  }
])

Find All:

db.posts.find()

Find with Condition:

db.posts.find({ likes: { $gte: 3 } })

Find using AND:

db.posts.find({
  $and: [
    { category: "Event" },
    { likes: 4 }
  ]
})

Find using AND with Condition:

db.posts.find({
  $and: [
    { category: "Event" },
    { likes: { $gt: 2 } }
  ]
})

Update One:

db.posts.updateOne(
  { title: "Post Title 4" },
  { $set: { likes: 5, category: "News" } }
)

Update Many:

db.posts.updateMany(
  { likes: { $gt: 2 } },
  { $set: { likes: 6 } }
)

Delete One:

db.posts.deleteOne({ title: "Post Title 3" })

Delete Many:

db.posts.deleteMany({ category: "News" })

Projection (show specific field):

db.users.find({}, { name: 1 })

Projection (hide _id):

db.users.find({}, { name: 1, _id: 0 })

Limit:

db.users.find().limit(3)

Skip:

db.users.find().skip(4)

Sort Ascending:

db.users.find().sort({ age: 1 })

Sort Descending with Skip and Limit:

db.users.find().sort({ age: -1 }).skip(2).limit(3)

MongoDB with Python:

from pymongo import MongoClient

client = MongoClient("mongodb://localhost:27017/")
print("Connected")

db = client["student_db"]
collection = db["students"]

student = {"name": "Rahul", "age": 21, "course": "BCA"}
collection.insert_one(student)
print("Data Inserted")

for s in collection.find():
    print(s)

collection.update_one(
    {"name": "Rahul"},
    {"$set": {"age": 22}}
)
print("Data Updated")

collection.delete_one({"name": "Rahul"})
print("Data Deleted")

---

