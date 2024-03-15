
# System Overview

Rocketship is a centralized control platform for orchestrating realtime reactive event relationships within networks of integrated systems. It provides an abstract, system-agnostic language and interface for defining and managing event relationships that lowers the technical barrier for designing interactive environments, and facilitates a more flexible and intuitive creative process.

## Basic Workflow

A physical device or **Machine** runs a local process called an **Executor**, that establishes a WebSocket client and connects to the Rocketship Core. An **Executor** publishes a list of **Targets** that represent interactable entities. A **Target** in turn holds a list of **Emitters**, which observe and report state changes, and **Actions**,  which provide commands for changing state.

Reactive event relationships are made by creating **Bindings** between **Emitters** and **Actions**, and are encapsulated by **Scenes** using the **Scene Graph**.

**Scenes** optionally have local **Event Tracks**, which allow precise control over how the **Scene** evolves in micro-time.

**Scenes** are optionally placed onto the **Calendar**, which schedules their activation and deactivation in global, macro-time.

## Components

- **Rocketship Core**: A centralized server, responsible for federating connected systems. (Can scale horizontally)

- **Machine**: A physical hardware device that runs an Instance.

- **Executor**: A local process running on a Machine that connects to the Rocketship Core and defines a Service schema.

- **Instance**: A copy of a Service, that ties a Service to an Executor.

NOTE: For some software, an Instance can be directly turned into an Executor with the addition of a plugin or module (e.g. Unreal Engine, TouchDesigner); for other software, the Executor must run as a separate process from the Instance (e.g. Pixera, Disguise). This decision is dependant on a per-integration basis, depending on the available software API. 

- **Cluster**: A group of Instances of the same Service.

NOTE: The Service abstraction layer allows the same Targets to belong to multiple Instances. Because Instances are ephemeral, Services are the persistent entity that own Targets, Actions, and Emitters.

- **Session**: A configuration of the above entities. A project can have multiple Sessions.

- **Target**: An interactable entity; the logical unit of control in a connected system.
	- **Emitter**: An observer and reporter of state changes for a Target.
		- **Pulse**: A momentary state change, broadcasted by an Emitter.
	- **Action**: A command for changing the state of a Target.
		- **Payload**: The data sent to execute an Action.

- **Binding**: A reactive event relationship made by connecting an Emitter to an Action.

- **Scene**: Encapsulates a set of Bindings; the logical unit of design.
	- **Scene Graph**: The interface for creating Bindings using Nodes.
	- **Node**: A unit of programming that lives on the Scene Graph; Emitters and Actions are Nodes, and there also exist a set of general Utility Nodes for creating more complex Bindings, as well as building other Scenes on or off.
	- **Event Track**: Each Scene has a local Event Track, which allows the Scene Graph to be modified over time.

- **Calendar**: The global, macro time where Scenes are scheduled to be activated and deactivated.

For more information, consult the [Rocketship Executor API](./02_Rocketship%20Executor%20API.md) and [Myko API](./03_Myko%20API.md).