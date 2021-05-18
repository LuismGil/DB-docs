# MongoDB

- 💃 MongoDB has a lot of flexibility and does not impose us to follow a well-defined structure or schema.
- 🙅 SQL imposes a very well-defined structure; it is super non-flexible.
- 🍻 With MongoDB it is easier to get started and add new features.
- ⏲ With SQL it is more time consuming to start because we must always have the order super clear. All items must have the same elements and all must be of the same type. If we want to add a new field we must add it everywhere with a default value, even if we don't need it.
- 🤒 If we don't follow good practices in MongoDB, we will need ultra-complex, delayed queries and a daily visit to the psychologist 😱.
- 💆 SQL's imposed order is not for nothing. Queries are easy to understand because everything follows its order and tranquility. Although, implementing new features takes time 🤔.

## Mongo operators

~~~
- $eq       =
- $gt       >
- $gte      >=
- $lt       <
- $lte      <=
- $ne       !=
- $in         Values within a range.
- $nin        Values that do not fall within a range.
- $and        Join queries with a logical AND.
- $not        Reverses the effect of a query.
- $nor        Join queries with a logical NOR.
- $or         Join queries with a logical OR.
- $exist      Documents that have a specific field.
- $type       Documents that have a field of a specific type.
- $all        Arrays containing all query elements.
- $elemMatch  Documents that meet the condition of the - $elemMatch in one of its elements.
- $size       Documents containing an array field of a specific size.
~~~

## Usage

With our cluster created from [Mongo Atlas](https://www.mongodb.com/cloud/atlas1).

- We connect by copying the link link in our terminal.

- `show dbs` (to observe our current databases).

- `use <baseName>` (to create a new database or join an existing one).

- We type `db` to make sure it was created correctly.

- Now we insert the following command to create a collection.

```
db.inventory.insertOne(
        { item: "canvas", qty: 100, tags: ["cotton"], size: { h: 28, w: 35.5, uom: "cm" } }
)
```

- ``show collections` (it will show us the collections we have created).

- To see information about the document we can filter with the `findOne()` function.

```
db.inventory.findOne()
```

- To connect from the interface [MongoDB Compass](https://www.mongodb.com/products/compass).

- We must connect using our username and password and linking our link.


- Database: 

  - Physical container of collections.

  - Each database has its own file in the file system.

  - A cluster can have multiple databases.

- Collections:

  - Grouping of documents.

  - Equivalent to a table in relational databases.

  - It does not impose a schema.

- Documents:

  - A record within a collection.

  - It is analogous to a JSON object (BSON).

  - The basic unit within MongoDB.


- To create a collection (optional) and add an item in JSON format: `db.COLLECTION_NAME.insertOne({ ... })`. The database responds true if the operation was successful and creates the unrepeatable _id field if we do not specify it.

- Create a collection (optional) and add some elements in JSON format: `db.COLLECTION_NAME.insertMany([{ ... }, { ... }])`. It receives an array of elements and returns all the IDs of the elements that were successfully created.

- Find elements in a collection: `db.COLLECTION_NAME.find()`.

- For a specific element we can apply the following `db.inventory.find({item: "canvas"})`. To this we can add a `pretty()` method to better see the result in the console.

- We can also apply a `count()` to know how many elements our operation returns.

- We can apply filters if we want to find only the first result with the `findOne()` method.

- We can also apply filters to this method.

- List all the possible commands that we can execute: `db.COLLECTION_NAME.help()`.

