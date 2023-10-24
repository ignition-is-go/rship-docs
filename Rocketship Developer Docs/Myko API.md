---
share: true
category: libs
---

Myko is an event sourcing library. Myko Servers host WebSocket gateways for clients to connect, and persist and sync data between server cluster members.
# Types

All Myko types have a pure data and are wrapped up with some metadata. This allows for lightweight data, use of language specific metadata, and other nice-to-have features in Myko Server Implementations. 

## Items

### MItem

these are the smallest unit as far as Myko is concerned. They have the minimum of the data below. It should be exended for each entity type your application cares about. 

> NOTE: the hash for each item can be omitted, and will be computed when the [[#MEvent]] that sets the item hits the server. It can, be provided if you would like to additionally limit recalculation, for example if there are fields which may change that do not warrant an update in the server. 

``` JSON
{
	id: "string", 
	hash: "string"
	... // other fields
}
```

### MWrappedItem

An [[#MItem]] wrapped with the string representation of it's type name. Necessary for including type information 

```JSON
{
	itemType: string, // entity name
	item: {
		... // full myko item
	}
}
```

### MEvent

Events extend the [[#MWrappedItem]], and are the source of truth for the history of Items. They are reduced by the Myko Servers to maintain their latest state. All Events are persisted for replay, and rollback by the servers. They are their own wrapped version, since they require no additional metadata

```JSON
{
	item: {...}, // the full item
	itemType: string,
	changeType: "SET" | "DEL",
	createdAt: string // ISO DateTime string
}
```

## Queries

###  MWrappedQuery

Queries are a request for data, which will be 

```JSON
{
	queryId: string, // query idenfier
	queryItemType: string, // itemType expected to return
	query: { 
		tx: string, // unique transaction id
	},
}
```

## Commands

### MWrappedCommand

Commands are a request to mutate state

```JSON
{
	commandId: string, // command identifier 
	command: {
		tx: string, // unique transaction id
		createdAt: string, // ISO DateTime string
	}
}
```



## WebSocket Api

The Myko WebSocket clients wrap the above types with some additional data to clearly identify the payloads to the server

## Connect

Connect to the Myko Server at `ws://SERVER_IP:5155/myko`

## Events

### WSMEvent

wraps an [[#MEvent]]

```JSON
{
	event: "ws:m:event",
	data: {
		clientId: string, //the id of your client
		... // the rest of the MEvent
	}
}
```

## Commands

### WSMCommand    

```JSON
{
	event: "ws:m:command", 
	data: {
		clientId: string, // the id of your client
		userToken: string?, // authentication token. server dependent.
		... // the full MWrappedCommand
	}
}
```

### WSMCommandResponse   

```JSON
{
	event: "ws:m:command-response",
	tx: string, // unique transaction id to match with command
	data: any, // any data returned by the command handler on the server
}
```

## Queries

### WSMQuery   

```JSON
{
	event: "ws:m:query",
	data: {
		clientId: string // the id of your client
		... // the full MWrappedQuery
	}
}
```

### WSMQueryResponse   

```JSON
{
	event: "ws:m:query-response",
	tx: string, // unique transaction id to match with query
	data: MWrappedItem[] // 
}
```