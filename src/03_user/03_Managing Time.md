# Managing Time

## Event Tracks

An Event Track is a reusable component for programming local, micro-time control. They contain Lanes which hold Keyframes.

Event Tracks can be thought of as deterministic, on-demand Targets. They are used within Scenes via the 'Fire Event Track' node. Event Tracks will play through their full duration unless stopped, and can be fired multiple times to create concurrent instances of the playback. 

If an Event Track is like a Target, its Lanes are like Emitters, and Keyframes are like Pulses. Each Lane is shown as an anchor on the right-hand side of the node which can be used like any other Emitter. 

## Calendar

The **Calendar** schedules Scene activation and deactivation in 'global', macro-time. 