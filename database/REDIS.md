# Redis

## Getters, Setters and Deletes
- SET <key> <value>
  - Returns "OK" if successful
- GET <key> <value>
  - If key does not exist, (nil) is returned
- DEL <key>
  - returns 1 if successful, otherwise 0

## TTL/Expiry of keys
- SET <key> <value>
- EXPIRE <key> <number of seconds>
  - returns 1 if TTL applied to a present key-value
  - returns 0 if TTL applied to an absent key-value
- TTL <key>
  - returns number of seconds left to expiry
  - returns -1 if a key-value has no expiry
- PERSIST <key>
  - removes the expiry of a key-value and persists it permanently
  - returns 1 if successfully applied on a present key-value
  - returns 0 if applied on an absent key-value

## Counter data structure
- INCR <key>
  - increment by 1
- INCRBY <key> <value>
  - increment by given value
- DECR <key>
  - decrement by 1
- DECRBY <key> <value>
  - decrement by given value
  
## List data structure
- RPUSH <key> <value> [<value>]
  - pushes the value to the start of the list, creating 1 if it does not exist
  - returns the total length of the list after the operation
  - can push more than 1 value
- LPUSH <key> <value> [<value>]
  - pushes the value to the end of the list
  - returns the total length of the list after the operation
  - can push more than 1 value
- LLEN <key>
  - returns the size of the list
- LRANGE <key> <starting index> <end index / -1 for end>
  - returns list of values
  
## Set data structure
- SADD <key> <value> [<value>]
  - adds value to key, creating set if not present
  - returns 1 if successful, 0 otherwise
  - if more than 1 value provided, returns the number of values successfully added
- SMEMBERS <key>
  - list members of set
  - returns list of values
- SISMEMBER <key> <value>
  - checks if value is found in set
  - returns 1 if is found, 0 otherwise
- SREM <key> <value>
  - removes value from set
  - returns 1 if successfully remove, 0 if value is not in set
- SUNION <key> <key>
  - returns unique values from both sets
- SPOP <key> <number of elements to pop>
  - removes the number of random elements (since set is not ordered) from the set
  - not recommended
  
## Sorted Set data structure
- ZADD <key> <sort value, number> <value>
  - once the sort value is taken up, it is no longer available for reassignment
- ZRANGE <key> <start index> <end index>
  
## Hash data structure
- maps between string fields and string values, usually used to represent objects
- HSET <key> <obj key> <obj value>
  - returns 1 if successful
- HGET <key> <obj key>
  - returns the obj value for the given obj key
- HGETALL <key>
  - returns the list with the key even and value odd
- HINCRBY <key> <obj key> <increment value>
  - increments the obj key with the given number
  - returns the subsequent value of that counter
  - use a negative number to decrement
  
