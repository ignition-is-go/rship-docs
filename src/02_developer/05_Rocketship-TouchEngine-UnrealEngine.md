# Rocketship-TouchEngine-UnrealEngine

Our goal is to pre-visualize a physical installation setup with Rocketship driving reactive event relationships between actors and content.

In this example, Unreal Engine (UE) provides a virtual twin of the space, and Touch Engine (TE) serves content. 
Rocketship provides the mechanism for creating reactive event relationships between the state of the space and the state of the content.

To accomplish this, we run a Rocketship Executor in TE (running inside UE), while also running a Rocketship Executor directly inside of UE.

The UE Executor is responsible for sending Emitters about the state of the level (actor position, number, density, etc.).
The TE Executor is responsible for taking Actions on content (affecting parameters, triggering effects, changing modes, etc.).

## Installation and Setup

1. Install the [Rship-UE Plugin](https://github.com/ignition-is-go/rocketship/releases)
    1. In the UE Project Settings, change the 'Game Instance Class' to RshipGameInstance.
    2. In the UE Project Settings, navigate to the 'Rship Exec' page (left sidebar under Plugins) and set the Rocketship Host address.

2. Install the [TouchEngine-UE Plugin](https://github.com/TouchDesigner/TouchEngine-UE/releases)

### Rship-UE Executor

1. Select any existing actor blueprint, or create a new blueprint class and select 'actor' as the parent class. 
2. Open the actor blueprint editor and add one or more 'Rship Target' components. Rename these components to the Target names you would like to surface in Rocketship.
3. Connect 'Rship Bind' nodes in the Event Graph to publish properties of the actor as Emitters.

### Rship-TE Executor

1. Place the 'RshipTouchDesignerExec.tox' or any .tox containing it into the UE project content folder.
2. Create a new blueprint class and select 'TouchEngineActor' from All Classes.
3. Open the blueprint editor and select the TouchEngine Component.
4. In the details pane, locate the 'Tox Asset' field and select the .tox to load.

## Tests

### Rship-TE Executor Validity

I create a simple TouchDesigner patch that renders a rectangle to an Out TOP. 
I load the RshipTouchDesignerExec.tox into the patch.
I create a BaseCOMP, label it 'rship', create a custom parameter 'color', and bind it to the rectangle's color parameter. 
I export the whole project as a .tox and load it into TouchEngine-UE. 
The Out TOP of the .tox (the rectangle) can now run in UE as a Texture Object Reference, and its color parameter is surfaced in Rocketship. 
With the level in play, I send a bundle from Rocketship to change the color of the rectangle and observe it change in UE.
I have successfully controlled a TouchDesigner patch running in Unreal Engine from Rocketship.

### Proof-of-Concept

In addition to the Rship-TE Executor I initialize the Rship-UE Executor, whose level reporter surfaces the positions of actors.
I bind the position of the player actor to the color of the rectangle - now, when the player moves, the color changes.

Rship-UE Executor | Rship-TE Executor
Emitter: Actor Pos| Action: Rectangle Color 

I have successfully created a reactive event relationship between actor and content in a virtual space. 