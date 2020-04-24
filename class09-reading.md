# API server

## Express: Router Parameters

- express can run MW on routes when only certain conditions are met
- `router.param('foo', func())` runs only when the `foo` parameter is on a route

## Sub Documents in Mongoose

- a schema can have other schemas within it to expand out further data
- not populated normally, a bit tricky to do as well
- no changes propgate automatically

## Joining data/docs in mongo

- `populate()` can connect 2 collections
  - method 1: via a reference to another collection
  - method 2: virtual population
    - create a virtual field in a doc pointed to a field in another doc
    - `pre(find)` makes a collection on the fly which is more efficient than storing relation
- pre/post hooks (MW)
  - mongoose let's you inject logic during lifecycle of data record
    - user can validate, normalize

### direct population (references)

- make a reference column in a collection, push in the `_id` of the referenced doc

### Virtual joins

- need to enable `virtuals` on the initial schema
- use named fields to connect
- `collection.pre('find', func)` will populate in real time

## Addtiional Resources

### articles

- [expres router.param() middlware](https://expressjs.com/en/4x/api.html#router.param)
- [mongoose middleware](https://mongoosejs.com/docs/middleware.html)
- [mongoose sub-documents](https://mongoosejs.com/docs/subdocs.html)
- [mongoose virtual joins](https://mongoosejs.com/docs/populate.html#populate-virtuals)
