# Class 04 Reading - Advanced Mongo/Mongoose

## [testing mongo](https://dev.to/paulasantamaria/testing-node-js-mongoose-with-an-in-memory-database-32np)

- mocking is sub-optimal as queries can change
- in-memory DB pro/con
  * PRO
  - no mocks needed
  - faster dev: can write just for the test query, don't need more beyond that
  - testing the code that will be in prod, not an old/incorrect/incomplete mock
  - easy test build: just seed the db and run the code
  * CON
  - need to seed the db
  - uses more memory
  - tests take longer to run

- TOOL: mongodb-memory-server

- create a schema

``` javascript
const productSchema = new mongoose.Schema({
  name: { type: String, required: true},
  price: { type: Number, required: true},
  description: {type: String},
});
<export>
```
- make the service

``` javascript
<import productModel>
module.exports.create = async (product) => {
  if (!product)
    throw new Error('Missing product');
    await productModel.create(product);
}
```

- configure jest
- runInBand makes tests run serially 

```javascript
"scripts": {
  "test": "jest --runInBand ./test"
}
```

- add to package.json

```javascript
"jest": {
    "testEnvironment": "node"
}
```

## [interfaces and repositories](https://cubettech.com/resources/blog/introduction-to-repository-design-pattern/)

- design patterns are tech agnostic
- biz logic goes to the repository, which THEN goes to the data source, and then back again
- Repository pattern is the container that holds the data
- if you couple that data without using a repository, you can make changing the controller very inflexible or complicated
- using a repo, you can swap out the database and just connect the handlers to without changing the biz logic