# 🧾 MongoDB Shell Commands & Results

---

### 🔹 use students
```javascript
use students
switched to db students
db.studentData.insertOne({ name: "Divya", age: 22, city: "Gudur" })
{
  acknowledged: true,
  insertedId: ObjectId("685fb1e7656d6911f5005181")
}
db.studentData.insertMany([
  { name: "Ravi", age: 24, city: "Chennai" },
  { name: "Meena", age: 21, city: "Hyderabad" }
])
{
  acknowledged: true,
  insertedIds: {
    "0": ObjectId("685fb1f1656d6911f5005182"),
    "1": ObjectId("685fb1f1656d6911f5005183")
  }
}
db.studentData.find({})
{ _id: ObjectId("685fb1e7656d6911f5005181"), name: "Divya", age: 22, city: "Gudur" }
{ _id: ObjectId("685fb1f1656d6911f5005182"), name: "Ravi", age: 24, city: "Chennai" }
{ _id: ObjectId("685fb1f1656d6911f5005183"), name: "Meena", age: 21, city: "Hyderabad" }
db.studentData.find({ city: "Gudur" })
db.studentData.find({ age: { $gt: 20 } })
db.studentData.find({ age: { $lt: 25 } })
