# Managing Bindings

The simplest Binding just connects an Emitter to an Action, but there is no limit to the complexity of a Binding.

Bindings can involve any number of Emitter and Action nodes, from any number of different Services.

It can be helpful to think of Bindings in terms of the topology of relationships they create between Targets of different Services:

- One-to-One
    - Binds an Emitter to an Action of two different Services
- One-to-Many
    - Binds an Emitter to multiple Actions of different Services
- Many-to-One
    - Binds multiple Emitters of different Services to an Action
- Self-Referential
    - Binds an Emitter to an Action of the same Service
- Reciprocal
    - Binds an Emitter of Service A to an Action of Service B, and an Emitter of Service B to an Action of Service A

These units can naturally be combined to produce more complex relational structures. 

## Utility Nodes

In addition to Emitters and Actions, Bindings can include additional logic via Utility Nodes:

- Space
    - Distance
    - Region Detect
    - Velocity
- Time
    - Sample
    - Trigger
    - Interval
- Generators
    - Wave
    - Value
- Logic
    - Gate
    - Threshold
    - Rerange
- Scene Control
    - Build Off
    - Build On
    - Fire Event Track
    - Scene Off
    - Scene On

- Lists (TBD)
    - TBD