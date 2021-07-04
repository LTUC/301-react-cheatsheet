# MongoDB Cheat Sheet

- Show All Databases

```shell
show dbs
```

- Show Current Database

```shell
db
```

- Create Or Switch Database

```shell
use db_name
```

- Drop

```shell
db.dropDatabase()
```

- Create Collection

```shell
db.createCollection('collection_name')
```

- Show Collections

```shell
show collections
```

- Insert Row

```shell
db.collection_name.insert({
  title: 'Post One',
  body: 'Body of post one',
  category: 'News',
  tags: ['news', 'events'],
  user: {
    name: 'John Doe',
    status: 'author'
  },
  date: Date()
})
```

- Insert Multiple Rows

```shell
db.collection_name.insertMany([
  {
    title: 'Post Two',
    body: 'Body of post two',
    category: 'Technology',
    date: Date()
  },
  {
    title: 'Post Three',
    body: 'Body of post three',
    category: 'News',
    date: Date()
  },
  {
    title: 'Post Four',
    body: 'Body of post three',
    category: 'Entertainment',
    date: Date()
  }
])
```

- Get All Rows

```shell
db.collection_name.find()
```

- Get All Rows Formatted

```shell
db.collection_name.find().pretty()
```

- Find Rows

```shell
db.collection_name.find({ category: 'News' })
```

- Sort Rows

```shell
# asc
db.collection_name.find().sort({ title: 1 }).pretty()
# desc
db.collection_name.find().sort({ title: -1 }).pretty()
```

- Count Rows

```shell
db.collection_name.find().count()
db.collection_name.find({ category: 'news' }).count()
```

- Limit Rows

```shell
db.collection_name.find().limit(2).pretty()
```

- Chaining

```shell
db.collection_name.find().limit(2).sort({ title: 1 }).pretty()
```

- Foreach

```shell
db.collection_name.find().forEach(function(doc) {
  print("Blog Post: " + doc.title)
})
```

- Find One Row

```shell
db.collection_name.findOne({ category: 'News' })
```

- Find Specific Fields

```shell
db.collection_name.find({ title: 'Post One' }, {
  title: 1,
  author: 1
})
```

- Update Row

```shell
db.collection_name.update({ title: 'Post Two' },
{
  title: 'Post Two',
  body: 'New body for post 2',
  date: Date()
},
{
  upsert: true
})
```

- Update Specific Field

```shell
db.collection_name.update({ title: 'Post Two' },
{
  $set: {
    body: 'Body for post 2',
    category: 'Technology'
  }
})
```

- Increment Field (\$inc)

```shell
db.collection_name.update({ title: 'Post Two' },
{
  $inc: {
    likes: 5
  }
})
```

- Rename Field

```shell
db.collection_name.update({ title: 'Post Two' },
{
  $rename: {
    likes: 'views'
  }
})
```

- Delete Row

```shell
db.collection_name.remove({ title: 'Post Four' })
```

- Sub-Documents

```shell
db.collection_name.update({ title: 'Post One' },
{
  $set: {
    comments: [
      {
        body: 'Comment One',
        user: 'Mary Williams',
        date: Date()
      },
      {
        body: 'Comment Two',
        user: 'Harry White',
        date: Date()
      }
    ]
  }
})
```

- Find By Element in Array (\$elemMatch)

```shell
db.collection_name.find({
  comments: {
     $elemMatch: {
       user: 'Mary Williams'
       }
    }
  }
)
```

- Add Index

```shell
db.collection_name.createIndex({ title: 'text' })
```

- Text Search

```shell
db.collection_name.find({
  $text: {
    $search: "\"Post O\""
    }
})
```

- Greater & Less Than

```shell
db.collection_name.find({ views: { $gt: 2 } })
db.collection_name.find({ views: { $gte: 7 } })
db.collection_name.find({ views: { $lt: 7 } })
db.collection_name.find({ views: { $lte: 7 } })
```
