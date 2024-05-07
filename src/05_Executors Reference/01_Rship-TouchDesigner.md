# Rship-TouchDesigner

The TouchDesigner Executor integrates naturally and easily with Rocketship. Simply load the rship .tox into any TouchDesigner network to eastablish a connection with Rocketship, tag the Base COMPs whose parameters you wish to expose with 'rship', and their custom paramaters will appear as Targets in the rship GUI with Emitters and Actions to observe/set each parameter's values. 

The Base COMP itself is also a Target and can be activated/deactivated with an Action.

Notch TOPs can also be tagged 'rship' to expose the parameters of the Notch page, as well as the parameter pages of every layer of the Notch block.

## Installation

> 1. Download the rship.tox
> 2. Import the rship.tox into your TouchDesigner project

## Setup

> 1. In the rship.tox, enter the address of the Rocketship Server you wish to connect to

## Usage

> 1. Add an 'rship' tag to a Base COMP
> 2. Create a custom parameters on the tagged Base COMP
> 3. Bind any other parameter in the network to the custom parameter 
>	1. Right-click on the parameter and click 'Copy Parameter'
>	2. Navigate back to the tagged Base COMP, right-click on the custom parameter, and select 'Paste Bind'
>   3. To export the output of a node to a custom parameter, drag the node onto the parameter name and select 'Export'
> 4. Pulse Reconnect on the rship.tox
> 5. Verify the Base COMP and its parameters appear in the Rship GUI as Targets

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