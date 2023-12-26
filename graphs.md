# Graphs

## Components 
* Nodes/Vertices - Objects, Entities
* Relationships/Edges - Connection

## Relationships/Edges
* Symmetrical Bi-directional - Relationship is bi-directional and same , Sam and Chai are in a marrige relationship with same amount of love reciprocating between them
* Asymmetrical Bi-directional - Relationship is bi-directional and same , Sam and Chai are in a marrige relationship but sam loves chai more
* One-directional - Relationship is one way, I work in a company or Live in a city

* For answering a question with graph the relationship and the weight between nodes plays important role
    - Ex - It depends if a journey route should cost efficient or time efficient to finalize the route.
* Traversing graph should be optimal and following the relationships. Neo4j Cypher query is optimised for this purpose

# Neo4j

* Each node can have labels which are tags which give more information about the node
* Each node can have Properties which are a Key-Value pairs giving details about a node
* Each relationship should be directional and should have a 'type' to show which relationships should be traversed for querying
* Each relaitonship can have Properties to give additional context
* Two Nodes can have multiple relationships between them

## Neo4j Native Graph Database
* Developed specifically for optimising traversal
* Index free adjacency if what differs it from other databases, For each transaction in database a reference to the relationship is stored with nodes both at start and end of relationship
* Since a node knows incoming/outgoing relationships already the tranversal in hardware goes just by passing through the pointers making it faster than search solutions we have with Databases.
* Joins made between data is done at Read time for RDBMS databases, thus as the amount of data increases it becomes slower, while for Neo4j it is built within the nodes making it fast.




## Neo4j
* Once we start the driver connection multiple TCP connections are established
* Each connection can be used as a session 
* A session can be used to perform multiple transactions
* A transaction is a unit of work done on database
* One problem with using session is the driver won't attempt retry for query if it fails. Because of this sessions are not used in production. Only for one time querying.
* execute_read and execure_write methods from session will take a method & parameters as inputs to execute a cypher query
* run method from session will take a cypher query to run directly
* session.begin_transaction()  from session can be used to start a transaction and run it manually with a query or rollback the transaction 
* Query results are consumed as a stram of records which can iterated over