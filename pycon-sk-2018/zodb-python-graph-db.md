# ZODB: The Graph database for Python Developers

https://2018.pycon.sk/en/speakers/Lozinski.html

- The competition is mostly in Java
  - They have a lot of money but there's a conceptual disconnect between Java DBs and Python projects
- Popular already in Plone projects
- Useful for social networks, Panama Papers investigaton, NLP for instance

## Usage

- You create Leaf objects
- Python native APIs (with magic methods) supported
  - NOTE: Code using it looks really truly elegant
  - Uses even the `del` keyword
- Has transactions, proper ACID database
- Has a web UI (?) with history and undo
- No schema needed
- Changes your mindset on how you think about graph problems
- There's an 'extended CRUD' with rename, cut/copy/paste, history
- The client implements a client-side cache
- Plenty of storage options; you can use blob file storage,
  but also DBs like Postgres, where it has support for nice indexes
- 1000s of transactions per second,
  80 TB of data with a thing called Neo (not to be confused with Neo4j)
- Not only the nodes, but also the links can have properties
- NOTE: Speaker plays video and apparently acts like it's a live demo? Tee-hee :D

## Questions

### Why this instead of JanusGraph of others?

- Java is statically bound, you have to redefine classes when adding attributes
- ZODB uses pickle to store any kind of objects

### How is concurrent access handled?

- Concurrent read is no problem
- Concurrent write is; it makes optimistic assumptions,
  adding nodes is okay, even incrementing is alright, but editing the same object will conflict
- The speaker didn't have any such problems in the use cases he needed ZODB for

### How does performance compare to NoSQL of SQL?

- Just writing records to a table, relational DBs are faster.
- If you need graphs, then it, of course, stands a better chance against 10 table joins or whatever.

### What projects should use a graph DB?

- Just map the real world with your DB.
  If you're working with a real life graph, like a social network, use a graph DB.
