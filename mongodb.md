## MongoDB
> Study notes related to MongoDB storage

#### Overview

`MongoDB` is document-oriented NoSQL storage system with flexible quering mechanism. 
Being that said, it mean that MongoDB do not store data in old fashioned table oriented manner.
Instead it store data in `Documents` with flexible schemas (each document can have uniq set of fields) and groups them in `Collections` that related to certain `database`. Mongo use `JavaScript` like language for perfoming query operations.

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
                                                              

#### Resources

> List of useful study resources

  - [Little MongoDB book](http://openmymind.net/mongodb.pdf)
  - MongoDB [Guide](https://www.tutorialspoint.com/mongodb/) on TutorialsPoint
    > Covers old version of Mongo but most core concepts are well defined

  - Official MongoDB [documentation](https://docs.mongodb.com/manual/) 
