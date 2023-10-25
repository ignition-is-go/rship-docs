# Table of Contents

1. [[1.0 What is Rocketship?]]
	1. [[1.1 Interactive Systems]]
	2. [[1.2 Reactive Event Handling]]
	3. [[1.3 Realtime]]
2. [[2.0 The Rocketship Architecture]]
	1. [[2.1 Targets and SubTargets]]
	2. [[2.2 Emitters, Pulses, and Actions]]
	3. [[2.3 Bundles]]
	4. [[2.4 Bindings]]
	5. [[2.5 Node Graphs]]
	6. [[2.6 Timelines]]
	7. [[2.7 Scenes]]
	8. [[2.8 Calendars]]
3. [[3.0 Getting Started]]
	1. [3.1 Connecting to a Rocketship Server](#3.1-connecting-to-a-rocketship-server)
	2. [[3.2 The GUI]]
	3. [[3.3 Projects View]]
	4. [[3.4 Dashboard View]]
	5. [[3.5 Configs View]]
	6. [[3.6 Bundles View]]
	7. [[3.7 Bindings View]]
	8. [[3.8 Scenes View]]
	9. [[3.9 Using Node Graphs]]
	10. [[3.10 Using Timelines]]
	11. [[3.11 Scheduling]]
	12. [[3.12 Emitter Status View]]
4. [[4.0 Executors, Targets, Actions, Emitters]]
	1. [[4.2 Unreal Engine]]

## [[1.0 What is Rocketship?]]

Rocketship is a creative tool that facilitates realtime, reactive event handling for complex multi-medium systems. Rocketship's centralized control platform enables creators to dynamically define, configure, and orchestrate **reactive event relationships**.

### [[1.1 Interactive Systems]]

Rocketship turns groups of independent systems into coordinated networks, enabling creators to leverage complex inter-system interactions for realizing artistic visions.

### [[1.2 Reactive Event Handling]]

**Events** are the state changes of a system that Rocketship can detect and/or trigger: any event in any system can trigger or be triggered by any other event in any other system. Rocketship uses **Events** as the creative building blocks of reactive relationships, thus allowing creators to form intricate cascading chains of reactions between different systems. 

### [[1.3 Realtime]]

Rocketship operates in realtime, ensuring that the systems in a network interact with each other fluidly and instantaneously. 

Realtime also means that creators can immediately bring their ideas into reality, thus increasing the velocity of creative iteration and development.

## [[2.0 The Rocketship Architecture]]

The Rocketship Architecture is a set of interrelated components that enable an operator to configure and manage reactive event relationships.

### [[2.1 Targets and SubTargets]]

A **System** publishes a list of its available **Targets**, which represents the elements of that system whose state changes can be observed and/or set. For organizational purposes, Rocketship allows **SubTargets** to be nested infinitely.

### [[2.2 Emitters, Pulses, and Actions]]

Each **Target** registers **Emitters** and **Actions**. An **Emitter** observes the **Target** and sends a **Pulse** *to* Rocketship whenever its state changes. Conversely, an **Action** is a command sent *from* Rocketship that sets the state of the **Target**.

### [[2.3 Bundles]]

Any number of **Actions**, from any number of different systems, may be grouped into a **Bundle**. When a **Bundle** is fired, all of the **Actions** it contains are sent simultaneously.

### [[2.4 Bindings]]

Creating a **Binding** instantiates the reactive relationship between an **Emitter** and a **Bundle**/**Action**. Whenever Rocketship receives a **Pulse** from the bound **Emitter**, it immediately fires the **Bundles**/**Actions** bound to that **Emitter**.

### [[2.5 Node Graphs]]

Rocketship allows fine-grained control over the parameters and logical flow of a **Binding** via **Node Graphs**.

**Nodes**:
- Threshold
	- Passes a value so long as the value is greater than or equal to the threshold
- Gate
	- Passes a value so long as the gate is open
- Sample
	- Samples the value of an **Emitter**
- Trigger
	- Allows you to create named triggers
- Value
	- Allows you to create named, keyframe-able, and shared values

### [[2.6 Timelines]]

In Rocketship, a **Timeline** is used to locally sequence the evolution of a reactive relationship. Each **Node** from the **Node Graph** is represented as a discrete 'lane' on the **Timeline**, and keyframe-like markers are placed on a lane to change the parameters of the corresponding **Node** over time.

### [[2.7 Scenes]]

A **Scene** encapsulates both a **Node Graph** and a **Timeline**. When a **Scene** is activated, its **Timeline** begins immediately. A keyframe on the **Timeline** of one **Scene** can also activate other **Scenes**.

### [[2.8 Calendars]]

Rocketship's **Calendar** situates **Scenes** in global time. In the **Calendar**, an operator determines the time frame for which a **Scene** is active, thus providing high-level control over when different reactive relationships are enabled.

## [[3.0 Getting Started]]

...

### [[3.1 Connecting to a Rocketship Server]]

We first need to connect a web browser to a Rocketship Server in order to load the Web GUI. Open up your favorite browser and navigate to the host IP address of the server you wish to connect to. 

Rocketship will ask you to authenticate yourself. In addition to security, this step also serves as a permissions mechanism for collaborative work.

### [[3.2 The GUI]]

Upon loading a project, you will see a navigation bar listing Rocketship's various pages: 

- [[3.3 Projects View]]
- [[3.4 Dashboard View]]
- [[3.5 Configs View]]
- [[3.6 Bundles View]]
- [[3.7 Bindings View]]
- [[3.8 Scenes View]]
- [[3.9 Using Node Graphs]]
- [[3.10 Using Timelines]]
- [[3.11 Scheduling]]
- [[3.12 Emitter Status View]]

Since Rocketship runs in a web browser you can duplicate the GUI in new tabs or windows, rearrange, and resize those windows as much as you'd like. We recommend dedicating at least two monitors towards operating Rocketship so that you can have a few different pages open at once.

At the bottom of the page lies a footer which lists the current [[version]], as well as the active [[config]] and [[session]] number. A single session may contain multiple configs.

You can view multiple configs at once by opening multiple windows - the color-coded footers will help you keep track of which windows correspond to which configs.

### [[3.3 Projects View]]

Create and name a new project. 

Data from systems connected with Rocketship (**Targets**, **Emitters**, etc.) persist between different projects, but anything you create within Rocketship (**Bundles**, **Bindings**, **Scenes**, etc.) is saved in the active project. 

Click on a project name to edit it.

### [[3.4 Dashboard View]] (Implementation TBD)

Don't worry if the **Dashboard** looks a bit empty - it's a running joke that Rocketship doesn't do anything. Rocketship populates its GUI based on the systems that are registered with it, so we need to connect at least one system (see [[Registering an Executor]]) in order for the GUI to emerge.

Dashboard components:
- Currently active scenes
- Total # of targets/emitters
- Total # of pulses per second
- List of scenes
	- Activate/deactivate scenes manually

### [[3.5 Configs View]]

==In **Configs** view (N.B. Are we keeping this view 3d, or transforming it into 2d? Also, are we setting up automated/default configs?==, you will see the **Machines** and their **Executors** that are registered with Rocketship, and whether they are currently available (connected) or unavailable (disconnected). ==You must connect an available **Executor** to ...  (N.B. Remind me what they get connected to?)== in order for Rocketship to function.

Create a new **Configuration**. Notice that you can now change a session's configuration directly from the footer.

### [[3.6 Bundles View]]

**Bundles** view contains a sidebar with a ==searchable and filterable (N.B. Add sorting functionality?) list of **Actions**, grouped by their respective **Targets** and **SubTargets**.== 

Create a **Bundle** and drag an **Action** into it. **Bundles** may be populated with any number of **Actions**. ==You can edit the data type of each action (N.B. Need to go over the information on each action card - what else can be edited? What datatype should be chosen? Why is the string field editable?).==

Make sure to ==save the **Bundle** (N.B. Make the save button larger/more obvious/labeled). You can manually Arm/Disarm and Send the **Bundle**.==

==(N.B. Since we are nixing the 3d view, **Bundles** view needs a way to manage and select different **Bundles**)==

### [[3.7 Bindings View]]

Similar to **Bundles** view, **Bindings** view contains a left-hand sidebar, this time with a list of **Emitters**. There is also a right-hand sidebar, where you should ==see the **Bundle** you just created (N.B. If a bundle is selected, it shows up in 'selected', but that's a bit confusing when you also see a 'bundles' category).==

Expand the **Target** structure until you find an **Emitter**. Notice that the **Emitter** card has a small heartbeat icon - whenever an **Emitter** sends a **Pulse** to Rocketship, its icon flashes. 

Click and drag an **Emitter** onto a **Bundle**. This will create a **Binding** in the middle column. ==Here, you can view and edit basic information about a **Binding** (N.B. Currently, when I create a Binding, the drop-down reveals nothing. And going forward: What information? What constitutes a **Simple Binding**, and how are they different from **Complex Bindings**? Could creating a Simple Binding auto-create a basic Node Graph?).==

### [[3.8 Scenes View]]  ==(N.B. Is the 'Scenes' overview being replaced by the Dashboard?)

In **Scenes** view, you can create and edit different **Scenes**.

Editing a **Scene** brings you to its **Node Graph** and **Timeline**.

### [[3.9 Using Node Graphs]]

Rocketship's **Node Graph** enables more fine-grained control over reactive event relationships.

Drag an **Emitter** and an **Action** from the sidebar onto the canvas. You will notice that an **Emitter** has one outlet, and an **Action** has one inlet. The shapes of the outlets and inlets determine valid connections between [[2.6 Nodes]].

Connect an **Emitter** to an **Action** to create a **Simple Binding**, then click 'Compile' to save the **Node Graph**.

### [[3.10 Using Timelines]]

...

### [[3.11 Scheduling]]

Use **Calendar View** to control when, in global time, **Scenes** are activated. 

### [[3.12 Emitter Status View]]

**Emitter Status** view illustrates the **Pulse** activity of **Emitters**. Similar to **Bundles** and **Bindings** view, **Emitters** are grouped by **Targets**. 

The collapsed **Emitter** graph simply plots a point whenever that **Emitter** fires a **Pulse**. 

The expanded **Emitter** graph, on the other hand, plots the *data value* of each **Pulse** over time.