# Rship-TouchDesigner

Rocketship integrates naturally with TouchDesigner. Simply load the rship .tox into any TouchDesigner network to eastablish a connection with Rocketship, tag the Base COMPs whose parameters you wish to expose with 'rship', and their custom paramaters will appear as Targets in the rship GUI with Emitters and Actions that observe/set each parameter's value. 

The Base COMP itself is also a Target with an Action to activate/deactivate (turn cooking on/off).

Rocketship has first-class support for Notch TOPs, which can also be tagged 'rship' to expose the parameters of the 'Notch' page, as well as the 'Parameters' page of each Notch layer in the block.

## Installation and Setup

1. Download the rship.tox
2. Import the rship.tox into a TouchDesigner project
3. In the rship.tox, enter the address of a Rocketship Server

## Usage: Base COMPs

1. Add an 'rship' tag to any Base COMP
2. Create a custom parameter on the tagged Base COMP
3. Bind any other parameter in the network to the custom parameter 
	1. Right-click on the parameter and click 'Copy Parameter'
    2. Navigate to the tagged Base COMP, right-click on the custom parameter, and select 'Paste Bind'
    3. To export the output of a node directly to a custom parameter, drag the node onto the custom parameter and select 'Export'
4. Pulse 'Reconnect' on the rship.tox

> NOTE: When tagging a new OP 'rship', you must pulse 'Reconnect' in order to register it. 
> When adding a new custom parameter to a Base COMP, you must either save the .toe or pulse 'Reconnect' to register it.

## Usage: Notch TOPs

1. Add an 'rship' tag to any Notch TOP

## Targets, Actions, and Emitters

| Targets            | Emitters                         | Actions                |
|--------------------|----------------------------------|------------------------|
| **Base COMPs**     |                                  | - Activate cooking     |
|                    |                                  | - Deactivate cooking   |
|                    | - Publish custom par values      | - Set custom par values|
| **Notch TOPs**     |                                  | - Activate cooking     |
|                    |                                  | - Deactivate cooking   |
|					 | - Publish Notch par values       | - Set Notch par values |
| **Notch Layers**   | - Publish layer par values       | - Set layer par values |