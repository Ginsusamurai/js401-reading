# Hash Tables

## resources

- [Intro To Hash Tables](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-30/resources/Hashtables.html)
- [What is a hash table?](https://www.youtube.com/watch?v=MfhjkfocRR0)
- [basics of has tables](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/)
- [hash table wiki](https://en.wikipedia.org/wiki/Hash_table)

## Terminology

- Hash > result of an algorithm obfuscating data programatically. in this context, used to determine index of array
- Buckets > what is in each index of the array of the hastable. An index could contain multiple key/val pairs if a collision occurs
- Collisions > when more than 1 key gets hashed to the same location on the hashtable

## why?

- Hold unique values
- dictionary
- library

## what?

- each `node/bucket` has a key/val
- a `hash` is encoding a key to a specific location for faster lookup

### example

`["Greenwood:98103", "Downtown:98101", "Alki Beach:98116", "Bainbridge Island:98110", ...]
`

- if we want to search this for a specific place, we need to iterate through the keys O(n) read time
- if we know the index, the speed is O(1)
- hash takes a key and gives an integer

## Structure

### hasing

- turns a `key` into an `integer`
- these need to be deterministic

### creating a hash

- hashtables are made from an array and you need a consistent size (like 1024)
- translate the key to a val. ex...
  1. add/mul all ASCII vals together
  2. multiply it by prime number such as 599
  3. use modulo to get the remainder of the result, when devided by the total size of array
  4. insert at that index

```javascript
Key = "Cat"
Value = "Josie"
67 + 97 + 116 = 280
280 * 599 = 69648
69648 % 1024 = 16
Key gets placed in index of 16.
```

- every bucket of the array starts as `null`

### collisions

- happen when 2 indexs collide, perfect has table doesn't have this
- collissions are solved by changing initial state of buckets
- we can make each bucket a `linked list` for safety
- if multiple key/vals in a bucket then we iterate through the bucket to find a matching key and return it's val which is ultimately much fewer iterations then the original array

### saving to hash table

- accept a key
- calculate the hash of the key
- use modulus to convert the hash into an array index
- store the key with the value by appending both to the end of a linked list

### reading from hash table

- accept a key
- calculate the hash of the key
- use modulus to convert the hash into an array index
- use the array index to access the short LinkedList representing a bucket
- search through the bucket looking for a node with a key/value pair that matches the key you were given

### Load Factor

- computs 'how full' the table is
- tables can grow if the load is too high

## Hash Table Methods

### Add

- send key to hash method
- go to the resulting index
- check for occupancy, add if empty
- if occupied, add to data structure

### Find

- take in key, hash it, go to index
- go through the bucket for the key/val pair

### contains

- accept key, return if key is in table
- call GetHash method, check table, iterate if need be

### GetHash

  - accept string, conduct has, return index for key/val to go