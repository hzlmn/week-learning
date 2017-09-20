## MongoDB
> Study notes related to MongoDB storage

#### Overview

`MongoDB` is document-oriented NoSQL storage system with flexible quering mechanism. 
Being that said, it mean that MongoDB do not store data in old fashioned table oriented manner.
Instead it store data in `Documents` with flexible schemas (each document can have uniq set of fields) and groups them in `Collections` that related to certain `database`. Mongo shell use `JavaScript` language for perfoming query operations.

#### Usage

  with Docker
  
  ```sh
  # some other Mongo images can be used
  $ docker -it mongo sh
  ```


  Mongo has cli tool `mongo` for quering database. Mongo default port `27017`

  Basic `mongo` usage

                                                                                                          
  MongoDB interactive shell client.                                                                     
                                                                                                        
- Connect to a database:                                                                         

  mongo database                                                                     
                                                                                                        
- Connect to a database running on a given host on a given port:                                        
                                                                                                        
  mongo --host host --port port database                                                                
                                                                                                        
- Connect to a database with a given username; user will be prompted for password:                      
                                                                                                        
  mongo --username username database --password                                                         
                                                                                                        
- Evaluate a javascript expression on the database:                                                     
                                                                                                        
  mongo --eval 'JSON.stringify(db.foo.findOne())' database                                              


#### Mongo collection operations

  - Find each document in collection

  ```js
  db.collection.find({})
  ```

  As an optional second parameter `find` accept projection.
  Projection is a way of enabling or disabling certain fields in final data.
  
  
  So for example, in such case we find all records and disable `_id` field
  
  ```js
  db.collection.find({}, {'_id': 0})
  ```
  

   - Insert document into collection
   > Note! use `insert_one` or `insert_many`, pure `insert` is supported but will be deprecated soon
  ```js
  // Insert single
  db.collection.insert_one({ 'name': 'Oleh' })

  //Insert many 
  // Everything is ok due to flexible schema
  db.collection.insert_many({'name': 'test'}, {'surname': 'test'})
  ```

   - Update document
  ```js
  db.collection.update(
    { '_id': ObjectId('some object id') }, 
    { '$set': {'data': 'updated_data'} }
  )
  ```

  - Using operating with query
  ```js
  db.collection.update(
    { 'age': { '$gt': 21 } }, 
    { '$set': { 'data': 'some test data' } }
  )
  ```

   - Updating multiple documents
  ```js
  db.collection.update(
    { 'age': { '$gt': 21 } }, 
    { '$set': { 'data': 'some test data' } },
    { 'multi': true }
  )
  ```

  - Using upserts

  > Upserts useful for matching document and if it exists updating it or creating new one

  ```js
  db.collection.update(
    { 'name': 'Oleh' }, 
    { '$set': { 'data': 'some test data' } },
    { 'upsert': true }
  )
  ```


   - Remove document from collection
  ```js
  db.collection.delete_one({ '_id': ObjectId('some_id') })
  ```

  More operationg can be found in docs


#### Data Modeling
> data modeling in NoSQL storages a bit different from traditional SQl based dbs.

Most common pitfall that Mongo don't have join mechanism so instead of performing joins of collections you just create two separete queries for each piece of data.

Mongo allows storing of nested structures, one document's size is limited to 16mb.


### When to use Mongo

  - Flexible schema
  - Logs
  - Storing nested structures ( eg. Three.js json models )
  - more ?


#### Data Aggregation
> TDB


#### Replication
> TBD

#### Sharding 
> TDB

#### Mongo clients

  - `motor` async Python3 client for `asyncio` / `Tornado`                                                           

#### Resources

> List of useful study resources

  - [Little MongoDB book](http://openmymind.net/mongodb.pdf)
  - MongoDB [Guide](https://www.tutorialspoint.com/mongodb/) on TutorialsPoint
    > Covers old version of Mongo but most core concepts are well defined

  - Official MongoDB [documentation](https://docs.mongodb.com/manual/) 
