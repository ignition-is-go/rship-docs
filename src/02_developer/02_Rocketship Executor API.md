# Rocketship Executor API

## General Modality

You are creating a module, plugin, or program that acts as the source of truth for the state of your connected System. You'll open a web socket connection to the Rocketship Core Server, to send updates, notifications, and other data, and to receive commands to change state.

> If you're using JavaScript/Typescript, the @rship/sdk library is your near-zero-config of getting connected easily, otherwise the full API is outlined below

## Getting Started
### Connect 
Executors must connect Connect to the Rocketship Websocket Server. Rocketship uses the [[Myko API]], so this is generally at `ws://${RSHIP_SERVER}[:MYKO_PORT]/myko`. 

> NOTE: The port is only required if the server is running in a development configuration. In deployed version, `/myko` is routed correctly by the reverse proxy

### Client ID

Upon connecting, your socket will receive a Command ([[Myko API#WSMCommand]]) that provides the `clientId` of your executor.
 
Please include this as `clientId` on any [[#Types]] that include the field
### Set Info

When the `clientId` is set, Send Events [Events](./Myko%20API.md) to `SET` any relevant types. Remember, this executor is the source of truth for these entities, so change them as they update, and 

For each [Target](#target), a [Target Status](#targetstatus) is required to set it as `online` for it to be displayed as such in the Rocketship UI

It is best practice to handle websocket reconnect logic, and resend all entities whenever your socket opens, as it will be given a new `clientId` at that time. 

## Types   

a brief description and the required fields (represented as Ts Types) for the relevant entity types are below

Please refer to the [Myko API](./Myko%20API.md) docs for important information about each item's `hash`

### Instance
Instances describe the running copy of your Service, under the responsibility of your executor. These should be identified uniquely as follows
- If more than one copy of the Service is running in your production environment under the purview of the same executor, they should be uniquely identified. 
- If more than one copy of the same Service is running under control of 2 different executors, they should also be uniquely identified. 
- If *the same* copy of your Service is find-able by more than one executor(fairly unlikely), it should only have one id to represent the actual topology of your network. 

```ts
{
	id: string 
	hash: string
	name: string
	serviceId: ID
	clientId: ID
	serviceTypeCode: string
}
```

### Target
These are the main unit of control in your system. They represent an entity that, generally speaking, is in one of many states at a time. This is not a harsh restriction, but is a good general guideline for what should be a Target. 

```ts
{
	id: string 
	hash: string
	name: string
	actionIds: ID[]
	emitterIds: ID[]
	subTargets: ID[]
	serviceId: ID
	bgColor: `#${string}`
	fgColor: `#${string}`
	lastUpdated: string
	category: string
	rootLevel: bool
}
```

### TargetStatus
Targets can be 'online' or 'offline' depending on whether their respective instances are started/available/open/etc. Targets Default to Offline

```ts
{
	targetId: ID,
	instanceId: ID,
	status: 'online' | 'offline'
}
```

### Action
These represent an action that your Target can take. These will be invoked later by the core, and are the main mechanism for changing the state of the target. A Target may have as many actions as you like, and every Action belongs to exactly one Target. Actions associated with one Target should *not* affect the state of another Target, unless that second target is a `subTarget` of the first target

```ts
{
	id: string, 
	hash: string,
	name: string,
	schema: string | null,
	targetId: ID,
	serviceId: ID
}
```

### Emitter
These are the publishers of state changes, or other impulses that can be consumed by the core. They can be thought of like topics or subscription subjects. 

```ts
{
	id: string, 
	hash: string,
	name: string,
	targetId: ID,
	serviceId: ID
}
```

### Pulse
Pulses are a data update of a Emitter. They belong to exactly one Emitter, and optionally carry data. 

```ts
{
	id: string, //this must be the same as the emitterId
	hash: string,
	emitterId: ID, // this is redundant data, included for compatability
	data: any
}
```


# Example

Providing a Target might look like this

```ts
{
	event: "ws:m:event",
	data: {
		itemType: "Target", 
		changeType: "SET", 
		createdAt: "2023-04-30T19:56:34Z",
		item: {	
			id: "banana-stand", 
			hash: "long-hash-string-of-some-kind",
			name: "The Banana Stand",
			actionIds: [
				"banana-stand:burn", 
				"banana-stand:fill-with-money"
			],
			emitterIds: [
				"banana-stand:banana-sold",
				"banana-sold:banana-tossed",
				"banana-stand:dollar-taken"
			],
			subTargets: [
				"cash-register"
			],
			serviceId: 'bluth-company',
			bgColor: `#ffff00`,
			fgColor: `#000000`,
			lastUpdated: "2023-04-30T19:56:34Z",
		}
	}
}
```

this payload should be stringified and then sent on the websocket to update the core about the nature of the target. 