
# System Overview

Rocketship is a centralized control platform for handling realtime reactive event relationships within networks of integrated subsystems. 

A subsystem or **Machine** runs a local **Executor** that connects with Rocketship via WebSocket. The **Executor** publishes a list of **Targets** that represent entities within the subsystem. A **Target** publishes a list of **Emitters** (observers of state changes) and **Actions** (mechanisms of state changes). An **Emitter** publishes **Pulses** that represent state changes, and optionally carry data.
### Components

- **Rocketship**: The centralized control platform.
- **Machine**: A subsystem connected to Rocketship.
- **Executor**: Local runtime within a Machine, connects to Rocketship via WebSocket.
	- **Service**: project file
	- **Instance**: copy of a project file
	- **Cluster**: grouped copies of the same Executor
- **Target**: Entity within a subsystem, managed by the Executor.
- **Emitter**: Observes state changes within a Target or SubTarget.
- **Action**: Mechanism for changing states within a Target or SubTarget.
- **Pulse**: Represents a state change, emitted by an Emitter.

### Structure

1. Executors running on Machines connect to Rocketship.
2. Executors publishes hierarchies of Targets and SubTargets.
3. Targets and SubTargets have Emitters and Actions.
4. Emitters emit Pulses.
5. Rocketship invokes Actions on Targets of Executors.

For more information, consult the [Myko API] and [Rocketship Executor API].

## System Design

### Web Stack:

1. One/Many Linux Servers
2. Docker
3. Docker Swarm
4. Kafka
5. Svelte



