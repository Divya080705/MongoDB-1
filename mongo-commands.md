

###  mongodb
```javascript
use students
switched to db students
###query1
db.studentData.insertOne({ name: "Divya", age: 22, city: "Gudur" })
{
  acknowledged: true,
  insertedId: ObjectId('685fb1e7656d6911f5005181')
}
###query2
db.studentData.insertMany([
  { name: "Ravi", age: 24, city: "Chennai" },
  { name: "Meena", age: 21, city: "Hyderabad" }
])
{
  acknowledged: true,
  insertedIds: {
    '0': ObjectId('685fb1f1656d6911f5005182'),
    '1': ObjectId('685fb1f1656d6911f5005183')
  }
}
###query3
db.studentData.find({})
{
  _id: ObjectId('685fb1e7656d6911f5005181'),
  name: 'Divya',
  age: 22,
  city: 'Gudur'
}
{
  _id: ObjectId('685fb1f1656d6911f5005182'),
  name: 'Ravi',
  age: 24,
  city: 'Chennai'
}
{
  _id: ObjectId('685fb1f1656d6911f5005183'),
  name: 'Meena',
  age: 21,
  city: 'Hyderabad'
}
###query4
db.studentData.find({ city: "Gudur" })
{
  _id: ObjectId('685fb1e7656d6911f5005181'),
  name: 'Divya',
  age: 22,
  city: 'Gudur'
}
###query5
db.studentData.find({ age: { $gt: 20 } })
{
  _id: ObjectId('685fb1e7656d6911f5005181'),
  name: 'Divya',
  age: 22,
  city: 'Gudur'
}
{
  _id: ObjectId('685fb1f1656d6911f5005182'),
  name: 'Ravi',
  age: 24,
  city: 'Chennai'
}
{
  _id: ObjectId('685fb1f1656d6911f5005183'),
  name: 'Meena',
  age: 21,
  city: 'Hyderabad'
}
###query6
db.studentData.find({ age: { $lt: 25 } })
{
  _id: ObjectId('685fb1e7656d6911f5005181'),
  name: 'Divya',
  age: 22,
  city: 'Gudur'
}
{
  _id: ObjectId('685fb1f1656d6911f5005182'),
  name: 'Ravi',
  age: 24,
  city: 'Chennai'
}
{
  _id: ObjectId('685fb1f1656d6911f5005183'),
  name: 'Meena',
  age: 21,
  city: 'Hyderabad'
}
###query7
db.studentData.find({
  $and: [
    { age: { $gt: 20 } },
    { city: "Gudur" }
  ]
})
{
  _id: ObjectId("685fb1e7656d6911f5005181"),
  name: "Divya",
  age: 22,
  city: "Gudur"
}



