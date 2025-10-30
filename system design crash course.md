- we never debug on production, instead we use staging environment to debug and catch the failure.
##### what makes a good design?
1. scalability: our sys growth with its user base
2. maintainability: future developers can understand and improve our system
3. efficiency: making the best use of our resources
4. reliability: planning for failure and building a system do well when things goes wrong.
#### heart of system design
heart of system design containing three elements:
1. moving data: data moving from one database to another securely
2. storing data: choose between SQL or no-SQL databases, it's about understanding access patterns, backup solutions and indexing strategies.
3. transforming data: turning row data into meaningful information
#### CAP Theorem
1. consistency: ensure all nodes of the system have the same data at the same time, change one node will reflect all nodes
2. availability: system always ready for requests, 24/7
3. partition tolerance: if a connection is interrupted between two nodes, system still working with no errors. 
`note`: according to CAP theorem, two of these can be achieved at same time.
`note`: CAP isn't about finding the perfect solution, it's about finding the best solution for our case.
#### API paradigms
###### REST:
stateless, with standard HTTP methods, it uses JSON and downside is `over-fetching` or `under-fetching`.
###### GraphQL:
1. avoid REST downside
2. strongly typed schema based queries
3. complex queries can impact sys performance
4. accept only POST request
5. returns with 200 always
###### gRPC:
1. built on HTTP2.0
2. multiplexing / server-push
3. uses protocol buffers
4. efficient
5. less human-readable
#### types of caching:
1. browser caching
2. server caching
3. database caching
4. CDNs