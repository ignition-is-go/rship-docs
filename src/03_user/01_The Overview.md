# The Overview

The Overview page provides a representation of the structure and activity within a Session.

Scenes are represented by cards, which contain a compact and reduced visualization of the Scene's Scene Graph. Actions and Emitters connected by lines indicate Bindings, and by zooming into the scene, more detailed information about its Targets (parent/child lineage, service, machine, etc.) is revealed. If a Binding contains any additional utility logic, that is also represented in a middle column between the Emitter and Action. 

The Scenes themselves are connected by lines that represent inter-scene activation logic. A connection line that goes from the right outlet of Scene A and into to the left inlet of Scene B, indicates that Scene A contains nodes which activate/deactivate or build-on/build-off Scene B.

The Overview uses a force-directed grid to automatically and dynamically rearrange connected Scenes, based on their height (which increases with the number of Targets in a Scene) and combinations of inter-scene activation structures (one to one, one to many, many to one, cycles, trees and forests, etc.).

Scenes which are not connected to any other Scene appear below, in a separate area.

## Manual Scene Control

Groups of Scenes can be selected by shift-clicking or box-selecting, and also by filtering via Service, Machine, Target, and other Scene properties. Once selected, Scenes can be manually armed/disarmed or activated/deactived. 

Refer to the on-screen legend (press '?') for information about Scene control keybindings.