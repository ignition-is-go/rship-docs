# Scenes, Node Graphs, and Timelines

A Scene enapsulates a collection of event relationships, and is represented by a node graph. Nodes are the emitters and actions of targets, bundles, and other useful utilities. By connecting an emitter node to an action node you create a binding.

A Scene can be activated and deactivated, and a scene's node graph is not functional unless the scene is active. Activation and deactivation can be triggered manually, by nodes in the node graph, or via scheduling the scene in the Calendar. When a scene is scheduled it will automatically activate and deactivate according to the time markers set in the Calendar. 

A Scene can own one or many Timelines (but isn't required to!). A Timeline sequences keyframes which modify parameters of the Scene's node graph.

Scene activation and deactivation represent important transition points, and so a Timeline can be assigned to the Scene's 'Activation Timelines' and/or 'Deactivation Timelines' group:
    - Upon Scene activation, all Timelines in the 'Activation Timelines' group will begin.
    - A Timeline in the 'Deactivation Timelines' group will automatically calculate when it needs to begin, in order to end upon Scene deactivation. 

If multiple Timelines are present in an Activation/Deactivation group, they can be start/end aligned relative to the longest Timeline of the group.

## Example UX Workflow

1. User creates a new scene (Scene 1)
    2. User adds nodes to the scene's node graph and creates bindings
        3. User creates a new 10-second timeline (Timeline 1)
            4. User adds keyframes to the timeline 
            5. User adds the timeline to the 'Activation Timelines' group
        6. User creates a new 5-second timeline (Timeline 2)
            7. User adds keyframes to the timeline
            8. User adds the timeline to the 'Activation Timelines' group
        9. User selects 'Align to End' for Timeline 2
        10. User creates a new 8-second timeline (Timeline 3)
            11. User adds keyframes to the timeline 
            12. User adds the timeline to the 'Deactivation Timelines' group
        13. User creates a new 6-second timeline (Timeline 4)
            14. User adds keyframes to the timeline
            15. User adds the timeline to the 'Deactivation Timelines' group
        16. User Selects 'Align to Start' for Timeline 4
