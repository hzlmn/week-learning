## Redis

> Learning notes related to Redis data store

`Redis` is lightweight, persistent key value data storage 

with flexible mechanism for organizing your data in terms of data structures

Redis is simple and performant

#### Usage

  with Docker

  ```sh
  $ docker pull redis
  ```

  ```sh
  $ docker run redis
  ```

  to enter container

  ```sh
  $ docker exec -it <container_id> sh
  ```

#### Use cases

 - Caching

    > As value access in redis is super fast it's popular alternative for varnish, memcached. 

 - Real time data

    > Redis often used for services that works with real time data. It has flexible mechanism for setting TTL for data. Due to exposing common data types you can achieve good perfomance when read-write your data.

#### Data types
  Redis not a simply key-value storage like Memcached it is better called data structures service.
  Redis has set of common builtin data types each has own set of accepted commands.
  Most common one are `String`, `Set`, `Hash`, `SortedSet`

  Common commands can be found [here](https://redis.io/commands)

#### Data modeling

  - Mostly you store string key-value pairs. For storing complex json like structures you just 
  use `json.loads` for stringifing it and store as pure string

  - If you need more control over qeuring you can store objects like `Hash` structure. But be aware that Redis do not allow you to store nested `Hashes`. Probably you need recap you data relation model for such cases.

  - For storing uniq uniq values you can use `Set` structure. Set has all common operations like union joins intersect , etc.

  - Common way for storing separate reccors of data but related to same domain like Users or Twits is by prefixing each record with `users:`. So sample user object can be stored as a key `users:{some_user_id}`. For quering such data you can use `keys` command with pattern, but it's not a recommended way. Better way will be to store user as a hashes, but if you need strctly this structure you can create separate `Set` that will hold user related keys. So then querining operation will be `O(x)` where `x` is `Set` length instead of `O(n)`
  where `n` is global number of keys.

  - There are lost of other recipes how to use Redis, but the beauty of Redis is that you can come with a way of how to you it that nobody thought about before. Redis is very flexible for all sorts of data storing operations.


#### Resouces

 - Little Redis book
 - Official Redis documentation
 - `aioredis` for async Python client 
