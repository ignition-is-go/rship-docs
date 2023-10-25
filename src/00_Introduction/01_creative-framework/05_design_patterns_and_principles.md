# Design Patterns and Principles

Consider a two-subsystem setup involving Ableton Live and Unreal Engine. To design a reactive event relationship following the constructivist approach, we begin by defining the events that will be involved and translating them into Rocketship's syntax.

From Ableton, we would like to consider playback state changes as events. The transport **Target** surfaces Ableton's playback state through an **Emitter** that emits a **Pulse** whenever the playback state changes. The **Pulse** data is binary; Ableton can either be 'playing' or 'not playing'.

From Unreal, we would like to consider the state changes of the color of a light as events. The light's **Target** component surfaces an **Action** to Rocketship which sets the color of the light. The **Action** data are continuous RGB values.

We can instantiate a basic relationship between these two events such that a change in Ableton's playback state leads to a change in Unreal's light color state. (This relationship would be classified as both Causal and Cross-Domain.) However, the relationship requires a rule and algorithm to handle the cross-domain interaction, since the data types of the **Pulses** (binary) and the **Actions** (continuous RGB) are dissimilar. The rule might state that a **Pulse** triggers the RGB values to be set to random values; or, that the RGB values be set to pre-defined values, for example 'green' when Ableton is playing and 'red' when Ableton is not playing. The algorithm carries out the rule, and is implemented in Unreal's event graph by inserting additional math and/or logic nodes between the 'Rocketship **Action**'' node and the 'set light color' node. It would also be possible to instead implement the data transformation algorithm in Rocketship's node graph, such that Unreal receives **Action** data already in RGB values.


