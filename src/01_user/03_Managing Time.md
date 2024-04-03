# Managing Time

## Event Tracks

An Event Track is a reusable component for programming fine-grained time control. They contain Lanes which hold Keyframes.

Event Tracks can be thought of as programmable, deterministic, on-demand Targets. They are used within Scenes via the 'Fire Event Track' node.

Lanes are like Emitters, and Keyframes are like Pulses, so each Lane of an Event Track is shown as an anchor on the right-hand side of the node. 

## Calendar

Scenes can optionally be added to the **Calendar**, which schedules when they are activated and deactivated in 'global' time. 