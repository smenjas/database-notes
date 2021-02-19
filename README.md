# Databases

## Data Persistence
We say that data __persists__ when our server remembers state after shutdown.
We persist data to non-volatile memory.  Volatile memory, like RAM, is fast but
expensive.  Non-volatile memory, like hard disks and solid state drives, are
slow and inexpensive, in comparison.  That's why we use both.

## Serialization
In order to save state, it's helpful to serialize it.  That means to convert it
into a string that describes the data accurately.

## Database Management System (DBMS)
A DBMS manages data on our storage, with various tradeoffs.  Some traits to
look for are:
- Atomicity
- Consistency
- Isolation
- Durability

See: [Wikipedia: ACID](https://en.wikipedia.org/wiki/ACID)

## Resources
- [SQL](sql.md)
  - [MySQL](mysql.md)
  - [SQLite](sqlite.md)
- NoSQL
  - [MongoDB](mongo.md)
