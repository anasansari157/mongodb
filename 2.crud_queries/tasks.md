1. Create a database named `blog`.

use blog

2. Create a collection called 'articles'.

db.createCollection("articles")

3. Insert multiple documents(at least 3) into articles. It should have fields

db.articles.insertMany([
  {author_name: 'Anas', title: 'JS', email: "anasansari@gmail.com"}, 
  {author_name: 'Sahil', title: 'CSS', email: "sahil@gmail.com"}, 
  {author_name: 'Jay', title: 'HTML', email: "jay@gmail.com"}
  ])


4. Find all the articles using `db.COLLECTION_NAME.find()`

db..articles.find()

5. Find a document using _id field.

db.articles.find({_id:  ObjectId("5e401333d2a0fdab747553b8")})

6. Find documents using title and author's name field.

db.users.find({}, {author_name: 1, title: 1, _id: 0})

7. Find document using a specific tag.

db.users.find({author_name: "Anas"})

8. Update title of a document using its _id field.

db.articles.updateOne(
   { _id:  ObjectId("5e401333d2a0fdab747553b8")},
   {
     $set: { "author_name": "Ashish" },
   }
)

9. Update a author's name using article's title.

db.articles.updateOne(
   { title: "CSS"},
   {
     $set: { "author_name": "Ashish" },
   }
)

10. rename details field to description from articles collection.

db.articles.updateMany( {}, { $rename: { "title": "tag" } } )

11. Add additional tag in a specific document.

db.articles.updateMany({}, {$set : {gender: 'male'}})

12. Update an article's tags using $set and without $set.
  - Write the differences here ?

  // $ set returns newer fields with older intact 
db.users.update({_id: 1234}, {$set : {gender: 'male'}})

// just object as update replaces older document
db.users.update({_id: 1234}, {gender: 'male'})

13. Increment an auhtor's age by 5.  

db.articles.update({name: "Ashish"}, {$inc: {age: 2}})

14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.

  db.articles.remove({name: "Ashish"});

Use sample.js data for below queries.

1. Find all males who play cricket.

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

3. Find all users who play either 'football' or 'cricket'.

4. Find all users whose name includes 'ri' in their name.

//Smaple.js is not related to this question
