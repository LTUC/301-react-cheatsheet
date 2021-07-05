# MongoDB Cheat Sheet

## Setup

To get setup with Mongoose you’ll have to have mongoose installed from npm using

```shell
npm install mongoose
```

Then you’ll need it required in your models and any js file where you are using it

```js
const mongoose = require("mongoose");
```

## Schema

The big difference between MongoJS and Mongoose is that Mongoose pushes you to create documents using a schema. You define a schema then create documents using that schema. With MongoJS on the other hand you’re free to do whatever you’d like. Some people prefer the freedom of MongoJS and some people prefer the structure of Mongoose. Since this is the major differentiating point we’ll start with creating a schema.

To create a schema your js will look something like this:

```js
const mongoose = require("mongoose");
const Schema = mongoose.Schema;

const ProductSchema = new Schema({
 
  name: {
    type: String,
    required: true
  },
  brand: {
    type: String,
    required: false
  },
  order: {
    type: Schema.Types.ObjectId,
    ref: "Order"
  }
});

// This creates our model from the above schema, using mongoose's model method
const Product = mongoose.model("Product", ProductSchema);

// Export the Article model
module.exports = Product;
```

## Creating documents based on the model

To use the model we need to import mongoose and the model. We have our model in a models folder so our code to do so looks like this

```js
const mongoose = require("mongoose");
const db = require("./models");
mongoose.connect("mongodb://localhost:27017/_YOUR_DB_NAME_", { useNewUrlParser: true });
```

Then we create a document like so

```js
const product = { name: "Soda", brand: "demoBrand" };
db.Product.create(product)
.then(function(dbProduct) {
    console.log(dbProduct);
})
.catch(function(err) {
    console.log(err);
});
```

## Mongoose CRUD methods

### Finding documents

- We can find all our documents (Products) with a command like below.

```js
db.Product.find({})
```

- Find a document based on id

```js
db.Product.findOne({ _id: <id> })
```

### Updating

- Update a single document

```js
db.Product.updateOne({ name: 'Soda' }, { brand: 'newBrand' });
```

- Update multiple documents

```js
db.Product.updateMany({ brand: 'demoBrand' }, { quantity: 500 });
```

### Delete Documents

- Delete a single document

```js
db.Product.deleteOne({ name: 'Soda' });
```

- Delete multiple documents

```js
db.Product.deleteMany({ quantity: { $gte: 100 } });
```

---

[Source Credit 🔗](https://kb.objectrocket.com/mongo-db/the-mongoose-cheat-sheet-225)

[⇐ GO BACK](../README.md)
