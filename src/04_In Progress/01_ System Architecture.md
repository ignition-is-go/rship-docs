## System Design

### Web Stack:

1. One/Many Linux Servers
2. Docker
3. Docker Swarm
4. Kafka
5. Svelte

# System Architecture

1. Myko
	- Buses (places for messages to flow through)
		- Command
			- Change data about entities
			- Have a transacton UUID
			- Happen upon GUI actions
			- Can also be called internally from Sagas
			- Command handlers create and publish Events
		- Event
			- Anytime something in the system changes, we publish an event of the type of the entity
				- Ex: Target entity, a class with properties/fields
			- Includes data about the item, Set or Delete
			- Publishes Set, Del, or All
		- Query
			- In charge of handling when somebody needs data
			- Receives JSON data queries from client, uses the query bus to look up the corresponding query handler, query handler returns query and passes result back to client
		- Report
			- Similar to query, but for arbitrary data
			- Specifically for things that are NOT entities
			- Values that are derived ONLY from the values of OTHER entities
	- MItems (common things between every Myko item) with types
		- Types of MItems represent Kafka topics
	- Any entity is an MItem plus its unique properties
	- Event reduction keeps the latest state of entities based on ID
	- Repos
		- Created for a particular entity type
		- Given the Event bus in order to listen to all events
		- Track all the Events using a hash map ID:Entity
		- Expose functions that give back streams, where each emission is an array of all entities that satisfy a query
	- Sagas
		- Turn events into commands
2. Core	
	- Things that can be used by both the client and server
	- Both a producer and consumer of all of the topics
		- Topic for each entity type
		- Everything in libs is an entity type
		- We think about streams of information as the hose/pipe they go through
			- Routing hoses, creating splits (information stream management)
3. Nest
	- Only used on the server
	- Implementation of things that support the main ideas
4. Kafka
	- Message broker 
	- Publish/Subscribe to messages on a given topic
	- Producers/Consumers
5. Svelte
	- Frontend implementation