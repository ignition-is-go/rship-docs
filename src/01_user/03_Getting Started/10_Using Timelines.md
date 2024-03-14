# Timelines

A Scene can own one or many Timelines (or none at all!). Timelines allow the Scene's node graph to be keyframed in local time (relative to the duration of the Scene).

A Timeline holds keyframes that modify the Scene's node graph. Any parameter of any node in the node graph can be keyframed.

A Timeline can be marked as an 'Activation Timeline' or 'Deactivation Timeline'. Activation Timelines run when the Scene is activated, and Deactivation Timelines run when the Scene is deactivated.

If multiple Timelines of different lengths are involved in the 'build on' or 'build off' transition, they can be aligned relative to the longest Timeline:

    - If a timeline is 'aligned to start', it will begin at the same moment as the longest timeline.
    - If a timeline is 'aligned to end', it will end at the same moment as the longest timeline.
