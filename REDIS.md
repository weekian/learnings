# Redis

## Getters and Setters
- SET <key> <value>
  - Returns "OK" if successful
- GET <key> <value>
  - If key does not exist, (nil) is returned

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
  
