# Class 03 reading - Data Modeling & NoSQL Databases

## JS data modeling

- to manipulate something, you first need to know (define) what it is
- JS has only the 5 main datatypes (obj, arr, str, num, bool)
- best practices are common but not mandatory
  - bool for only 2 states
  - num when arithmetic operators might happen
  - str for language
  - arr for bundled data
  - obj for many layers of bundled data

## CRUD
- Create
- Read
- Update
- Delete

## Interfaces and Services - the 'Repository' design pattern

- services connect the operation to the data source (whatever it may be)

## Implementation

- implementation is the means of interating with the persistence layer (file, mongo, postgres)

## Normalization and Validation

- sanity check data before operating it to ensure proper format

## NoSQL database

- 'norma/tradtional' DBs like postgres, sql server, oracle are 'relational' (store in rows and columns) and link records via keys
- use a special language to access data
- noSql -> document storage based. Rather than data spread across records, it's all in 1 record (like a doc page)
- typically they are pure json, no real structure.
- good for 'read-heavy' usage and frequent aggregations

-noSql data modeling
  - start with what you need, rather than available data
  - you can have multiple docs if needed,the write time is expensive but the read is worth it

- ORM(mongoose) Object Relation Mapping - used for the service layer
- need a schema for the data types (type, required, case, enum, etc.)


-Cloud Databases
--There are a few alternatives to running Mongo locally for your web servers

- [MLab](https://www.mlab.com/) - remotely hosted mongoDB systems. Easily setup a free database (or pay for more horsepower). Works great with Heroku
- [Atlas](https://www.mongodb.com/cloud/atlas) - Cloud based, highly scalable Mongo DB
- [DynamoDB](https://aws.amazon.com/dynamodb/) - AWS NoSQL Database. Very highly scalable. Also provides a ‘mongoose’-like ORM called ‘dynamoose’
- [CosmosDB](https://cosmos.azure.com/) - The Microsoft Azure equivalent for Atlas and Dynamo

### Videos
- [sql vs nosql](https://www.youtube.com/watch?v=ZS_kXvOeQ5Y)
### Bookmark / Skim
- [nosql vs sql](https://www.thegeekstuff.com/2014/01/sql-vs-nosql-db/?utm_source=tuicool)
- [nosql modeling techniques](https://highlyscalable.wordpress.com/2012/03/01/nosql-data-modeling-techniques/)
- [mongoose api](https://mongoosejs.com/docs/api.html#Model)