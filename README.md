Got it — I’ve extracted and organized all code from your NGD experiments and converted it into a clean README.md style document you can directly use for GitHub or submission.


---

📘 README – Next Generation Database Lab (MongoDB)

👨‍🎓 Student Details

Name: Tanuj Narula

Course: AIDS-A

Subject: Next Generation Databases Lab



---

🧠 Experiment 1: MongoDB Setup

▶️ Start MongoDB Shell

mongosh


---

⚙️ Experiment 2: Database Operations

▶️ Create / Switch Database

use mydb

▶️ Show Databases

show dbs

▶️ Show Current Database

db

▶️ Drop Database

db.dropDatabase()


---

📦 Experiment 3: Create Collection

▶️ Create Collection

db.createCollection("students")

▶️ Show Collections

show collections


---

⚙️ Experiment 4: Collection Options & Drop

▶️ Create Collection with Options

db.createCollection("col6", {
  capped: true,
  autoIndexId: true,
  size: 5000,
  max: 10000
})

▶️ Drop Collection

db.col5.drop()


---

🔁 Experiment 5: CRUD Operations

▶️ Insert One

db.posts.insertOne({
  title: "Post Title 1",
  body: "Body of post.",
  category: "News",
  likes: 1,
  tags: ["news", "events"],
  date: Date()
})

▶️ Insert Many

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

▶️ Find All

db.posts.find()

▶️ Find with Condition

db.posts.find({ likes: { $gte: 3 } })

▶️ Find using AND

db.posts.find({
  $and: [
    { category: "Event" },
    { likes: 4 }
  ]
})

▶️ Find using AND + Condition

db.posts.find({
  $and: [
    { category: "Event" },
    { likes: { $gt: 2 } }
  ]
})

▶️ Update One

db.posts.updateOne(
  { title: "Post Title 4" },
  { $set: { likes: 5, category: "News" } }
)

▶️ Update Many

db.posts.updateMany(
  { likes: { $gt: 2 } },
  { $set: { likes: 6 } }
)

▶️ Delete One

db.posts.deleteOne({ title: "Post Title 3" })

▶️ Delete Many

db.posts.deleteMany({ category: "News" })


---

🔎 Experiment 6: Projection

▶️ Show Specific Field

db.users.find({}, { name: 1 })

▶️ Hide _id Field

db.users.find({}, { name: 1, _id: 0 })


---

📊 Experiment 7: Cursor Methods

▶️ Limit

db.users.find().limit(3)

▶️ Skip

db.users.find().skip(4)

▶️ Sort Ascending

db.users.find().sort({ age: 1 })

▶️ Sort Descending + Skip + Limit

db.users.find().sort({ age: -1 }).skip(2).limit(3)


---

🐍 Experiment 10: MongoDB with Python

▶️ Connect to MongoDB

from pymongo import MongoClient

client = MongoClient("mongodb://localhost:27017/")
print("Connected")

▶️ Create Database & Collection

db = client["student_db"]
collection = db["students"]

▶️ Insert Data

student = {"name": "Rahul", "age": 21, "course": "BCA"}
collection.insert_one(student)
print("Data Inserted")

▶️ Read Data

for s in collection.find():
    print(s)

▶️ Update Data

collection.update_one(
    {"name": "Rahul"},
    {"$set": {"age": 22}}
)
print("Data Updated")

▶️ Delete Data

collection.delete_one({"name": "Rahul"})
print("Data Deleted")


---

🎯 Conclusion

This lab covers:

MongoDB basics

Database & collection operations

CRUD operations

Query operators

Projection

Cursor methods (limit, skip, sort)

MongoDB integration with Python using PyMongo



---

🚀 Optional (for GitHub enhancement)

You can add:

Screenshots of output

Explanation sections

Viva questions



---

If you want, I can: ✅ Convert this into perfect GitHub README with badges & formatting
✅ Add theory + explanation under each code block
✅ Or make a PDF report ready for submission

Just tell me 👍
