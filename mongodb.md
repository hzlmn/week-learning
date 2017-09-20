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

   - Remove document from collection
  ```js
  db.collection.delete_one({ '_id': ObjectId('some_id') })
  ```

  More operationg can be found in docs


#### Data Aggregation
> TDB

#### Data Relations
> TBD


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
