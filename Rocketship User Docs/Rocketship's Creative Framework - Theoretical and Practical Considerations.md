# Contents

0. Introduction
1. Classes of Reactive Event Relationships
2. Rules and Algorithms
3. Properties of Reactive Event Relationships
4. Complexity
5. Design Patterns and Principles
6. Relationships Between Relationships
# 0. Introduction

This paper attempts to explore the unique creative framework that emerges when considering Rocketship's 'realtime reactive event relationships' as creative building blocks for designing experiences using complex multi-medium systems. A creative framework encompasses the fundamental principles, practices, tools, and methodologies used within a particular approach to creative exploration and ideation. The 'creative building blocks' of a given framework dictate, to an extent, the boundaries of creative possibility that can be conceived within that framework. 

It would seem rare to find someone who naturally conceives of a reactive event relationship constructively, by first considering the events involved, then the class of the relationship, then its rules and algorithms, its properties and attributes, and finally the ways it might relate to other relationships in a broader context. More likely, people naturally conceive of reactive event relationships intuitively, by imagining a hypothetical reality in which the relationship exists in order to explain how the effects of a certain relationship would lead to a certain experience. It feels so natural to conceive of reactive event relationships in this way because they are so fundamental to our experience of life - anything could be considered an event, and any event could react to any other event. 

Because we assemble our conception of reactive event relationships primarily through experience, and only secondarily through intellectual consideration, it is difficult to imagine relationships that lead to experiences we've never had. I hope that the theoretical and practical concepts discussed herein provide a useful starting point for retrospectively describing reactive event relationships conceived intuitively, as well as expanding the scope of possibility for constructing new kinds of relationships. My aim is to aid the prospective creative designer and Rocketship operator in navigating the process of defining, organizing, and managing reactive event relationships, as well as dealing with the complex possibility-space that grows exponentially as the number, complexity, and diversity of different subsystems increases.  

The set of reactive event relationships that we can conceive of is limited only by our imaginations. And yet, it's easy to imagine an experience where you flap your arms and a bunch of pigs pour out of the sky riding rainbows, but it would be another matter entirely to instantiate a realtime reactive event relationship between 'man-flaps-arms' and 'pigs-ride-rainbows'. The physical and technological limitations of reality do impose a hard boundary on the set of reactive event relationships which are possible to practically instantiate and control. (Happily, we can in fact make virtual pigs fly.)

The other, more 'soft' boundary stems from the artistic and/or functional context in which a relationship is conceived and implemented. For instance, a vertically-integrated installation job with little role distinction between creator, artist, and designer offers near-unlimited creative freedom for designing the system and subsystem structure and the realtime reactive event relationships therein. On the other end of the spectrum, a creator/artist might wish to only use Rocketship to implement a particular relationship they have already conceived of, thus limiting the Rocketship operator's role to simply programming a preconceived relationship, rather than exploring what relationships are possible to create within the bounds of the system.

That being said, it's no trivial matter to just simply 'explore what relationships are possible to create within the bounds of a system', not least of which because a relationship does indeed need to be programmed into Rocketship in order for it to be instantiated. Generally speaking, the process of creating reactive event relationships in Rocketship proceeds by determining:

1. The system and subsystem structure (**Executors, Instances, Clusters, Services, and Targets**).
2. The set of events each subsystem can surface to Rocketship (**Emitters and Actions**).
3. The events to be involved in a reactive relationship (**Binding**).
4. The nature of the relationship itself, which can be described intuitively and/or by its:
	1. Class
	2. Rules and Algorithms
	3. Properties

**Chapter 1** reviews the basic classes of relationships, and **Chapter 2** the types of rules and algorithms which govern the behavior of those relationships. **Chapter 3** examines through a practical lens the various properties of relationships, and touches on concepts such as determinism, chaos, time, recursion, and self-similarity. **Chapter 4** explores a number of different types of emergent complexity. **Chapter 5** observes, from a creative design perspective, the overarching patterns and principles for creating realtime reactive event relationships, and finally **Chapter 6** suggests some strategies for organizing and managing the relationships that exist between reactive event relationships.
## Terminology

1. **System/Network:** The overarching, total system, defined by the network of its subsystems/component systems.
2. **Subsystems/Components:** The individual components that together make up the whole system.
3. **Rocketship:** The centralized control platform subsystem which facilitates bi-directional communication throughout the system.
4. **Communication Infrastructure**: The medium through which different subsystems connect and interact with each other through Rocketship.
5. **Architecture**: The underlying structure that dictates how different subsystems connect and interact with each other.
	1. **Target:** Some element of a subsystem whose state changes can be observed and set.
	2. **Emitter/Pulse:** An **Emitter** observes an element and sends a **Pulse** *to* Rocketship whenever its state changes.
	3. **Action/Bundle:** An **Action** is a command sent *from* Rocketship that sets the state of an element. A **Bundle** is a group of **Actions**.
	4. **Binding:** The mechanism which instantiates a reactive event relationship.
6. **Realtime Reactive Event Relationships:** The interactions that occur within and between subsystems. A reactive event relationship is considered 'realtime' if there is no perceived latency between the two events.

**Rocketship** transforms groups of isolated **subsystems** into interactive, interconnected, dynamically reactive **networks**. It provides the **communication infrastructure** and underlying **architecture** necessary for creating and sequencing **realtime reactive event relationships** within and between different subsystems.
# 1. Classes of Reactive Event Relationships

After determining the events involved in a relationship, it remains to consider the nature of the relationship itself, which is largely informed by its class:

1. **Causal Relationships:** These are the most direct and straightforward relationships, and occur when a state change in one subsystem (the cause) triggers a state change in another subsystem (the effect).
2. **Self-Referential Relationships:** A relationship is considered self-referential when the state change of a subsystem triggers a state change in the same subsystem.
3. **Reciprocal Relationships:** In a reciprocal relationship, a state change in one subsystem triggers a state change in another, which in turn triggers a state change in the initial subsystem.

Both self-referential and reciprocal relationships can give rise to positive (amplification) and negative (stabilization) feedback loops, whereby a state change leads to more or less of the same change.

4. **Multidirectional Relationships:** In a Multidirectional Relationship, a single subsystem impacts and is impacted by multiple other subsystems, creating a complex and interconnected network of influence.
5. **Hierarchical/Ordered Relationships**: These are formed when multiple causal relationships are structured in a hierarchical order.
6. **Cross-Domain Relationships**: Cross-domain relationships span different types or domains of subsystems.
7. **Dynamic Relationships:** In a Dynamic Relationship, the nature of the relationship itself evolves over time. Dynamic Relationships can demonstrate adaptation and learning, responsiveness to environmental context, and even emergent behavior.

Relationships can certainly be of multiple classes at once

From a creative design perspective, these classes offer choices for determining the basic form of a reactive event relationship. They can also be used to retrospectively describe and organize reactive event relationships conceived intuitively.
# 2. Rules and Algorithms

Rules and algorithms define the constraints, conditions, procedures, and overall behavior of reactive event relationships.

==Note that there is always a compromise between the rules and algorithms owned by Rocketship, and those by subsystems.==

For the sake of example, imagine that Rocketship has transformed all of your house's various subsystems (lighting, heating/cooling, security, appliances, entertainment - anything you can manage to connect with Rocketship) into a dynamically reactive network. You, Lord and Overseer of this newly operational Mega Smart Home, overlook a holographic dashboard describing the various states of all the different reactive event relationships at work. 

![[Wind Chimes.png]]

A soft breeze blows through the wind chime hanging just outside your window, and (if it's a Tuesday) the intensity of your lights smoothly modulate according to the amplitude of the wind chimes. 
## **Cross-Domain Interactions:**

   - **Rules**: Define how events of different domains react to each other.
   - **Algorithms**: Procedures for data normalization and transformation.
      - **Example**: The rule states that light intensity reacts to wind chime amplitude. The algorithm normalizes amplitude **Pulse** data and transforms it into light intensity **Action** data.
## **Emitters:**

   - **Rules**: Conditions for an **Emitter** to send a **Pulse**; ==owned by the **Executor** and settable by Rocketship.==
   - **Algorithms**: Procedures for checking **Emitter** conditions.
      - **Example**: The rule states that an audio analysis **Emitter** sends amplitude data **Pulses** to Rocketship only while the chimes exceed an amplitude threshold. The algorithm analyzes the audio, and while the chimes are ringing, sends **Pulses** to Rocketship.

## **Bindings:**

   - **Rules**: Conditions for a **Pulse** to trigger an **Action**; ==only owned and settable by Rocketship.==
   - **Algorithms**: Procedures for checking **Binding** conditions.
      - **Example**: The rule states that **Actions** are only triggered by wind chime amplitude **Pulses** if it's a Tuesday. The algorithm determines if it's a Tuesday and, if so, activates the binding.

## **Actions:**

   - **Rules**: Conditions that govern the **Actions** themselves; ==can be owned and set by both **Executors** and Rocketship.==
   - **Algorithms**: Procedures for checking **Action** conditions.
      - **Example**: The rule states that light intensity **Actions** (bound to the wind chime **Emitter**) must be interpolated, in order to avoid abrupt shifts. The algorithm interpolates the intensity of the light between peak values at a given sample rate.

You've also set up a reactive event relationship to modulate the room's ambient music level according to the amplitude of the wind chimes (this one is not a **Cross-Domain Relationship**). But the once-soft wind blows more strongly now, causing the wind chimes to ring loudly and frequently, and disrupting the serene atmosphere by causing the lights to flicker too often and the volume of the music to swing erratically. Luckily, a feedback loop can ensure that harmonious ambiance is maintained.
## **Feedback Loops:**

   - **Rules**: Specify when and how feedback loops are initiated, maintained, or broken.
   - **Algorithms**: Methods for monitoring and controlling feedback loops.
      - **Example**: The rule states that as the wind chime's amplitude **Pulses** become louder and more frequent (indicating strong wind), the **Pulse** values are scaled down, and if no **Pulses** are detected for a given duration, the scaling factor is reset. The algorithm tracks the frequency and amplitude of wind chime **Pulses**, and gradually adjusts the scaling factor of the **Emitter** accordingly.

The light intensity and music level are smoothly reacting to the amplitude of the wind chimes, but even though there's a breeze, it's getting a bit hot in here. As the room heats up from the midday sun, a temperature sensor's threshold is exceeded, and three reactive event relationships you've programmed kick into gear. All three relationships involve the temperature sensor, but one connects the sensor to the window, another to the window blinds, and another to the A/C.

## **Multidirectional Relationships:**
   - **Rules**: Govern interactions of a subsystem with multiple others.
   - **Algorithms**: Manage priority, sequencing, and coordination.
      - **Example**: The rule states that when the temperature exceeds a certain threshold during daylight hours, the window, window blinds, and A/C system should coordinate to lower the temperature. The algorithm first checks the time of day to ensure that it's daylight. If it is, the blinds are lowered to block out direct sunlight. Simultaneously, the algorithm evaluates the internal temperature against the outdoor temperature. If the outdoor temperature is cooler, it opens the window instead of activating the A/C; if not, it activates the A/C system.

The only thing that could possibly disrupt this perfectly splendid afternoon would be uninvited guests. Luckily, the Mega Smart Home boasts some impressive security capabilities - a modern take on the feudal kingdoms of old.

You (Lord and Overseer) have a second-in-command robo-Queen, the ultimate security decision-maker. If the Queen receives too many reports of threats, they will declare a state of emergency. The Queen commands her robo-Ladies, who oversee the different territories of the kingdom. They take action on minor threats but escalate bigger issues to the Queen. Each Lady manages a group of robo-Knights, the frontline warriors responsible for detecting threats and reporting to their respective Ladies. 

## **Hierarchical Relationships:**

   - **Rules**: Define the structure of the hierarchy (parent-child relationships, priority, and overriding) and how reactions propagate through it.
   - **Algorithms**: Enforce the hierarchy, manage the flow of reactions, and handle any conflicts or exceptions.
      - **Example**: The rule states that Knights report all incidents to their respective Lady, and that Ladies handle minor issues but escalate major threats to the Queen. The algorithm enforces that when three or more Knights report a threat to a Lady, the "Gentle Reminder" defense subsystem is activated. If a Lady deems a threat to be major, she activates the "Not-So-Subtle Hint" and escalates the issue to the Queen. If the Queen is notified of multiple threats, she declares a state of emergency and activates "Dante's Inferno".

As the sun begins to set and darkness settles in, you begin to feel that the lights (bound to the wind chimes) are now flickering too wildly for how dark it is, so you make the reactive event relationship dynamic.

## **Dynamic Relationships:**

   - **Rules**: Regulate how relationships adapt or evolve over time.
   - **Algorithms**: Control and implement dynamic adaptations.
      - **Example**: The rule states that the scaling factor of the 'wind chime-light intensity' relationship should change relative to the position of the sun. The algorithm checks the position of the sun and adjusts the scaling factor accordingly.

Night deepens and you retreat further into your chambers, resting easy not only because of your Medieval robo-legion, but also because Rocketship ensures that your Mega Smart Home will never reach an undesirable or harmful state.

## **System Safety:**

- **Rules**: Prevent the system from reaching undesirable or potentially harmful states.
- **Algorithms**: Specific methods for detecting and handling potential issues, including recovery procedures or fail-overs.
- **Example**: 
	- The rule states that no matter how strong the wind, the 'wind chime-light intensity' relationship has a limit, ensuring the lights don't flash too brightly or rapidly. Moreover, if the system detects erratic or inconsistent pulses, perhaps due to a faulty sensor, it defaults to a neutral state, preventing any erratic behavior. The algorithm monitors the frequency of pulses, and if they exceed a set threshold within a short time, the system overrides any dynamic rules and sets the lights to a gentle, predefined glow.

# 3. Properties of Reactive Event Relationships

In addition to its class, a reactive event relationship can be further described by the properties and qualities it exhibits.
## Determinism and Chaos

Determinism refers to the degree to which reactive event relationships and their resulting effects within the system are predictable and consistent, given a particular initial condition and set of rules/algorithms.

Factors that can introduce non-determinism include:

1. **Randomness:** If the system includes randomness, such as random number generators or other stochastic elements, it will not be strictly deterministic, as these elements can lead to different outcomes despite having the same initial conditions.

2. **External Inputs:** If the system interacts with unpredictable external elements, like user input or environmental conditions, these state changes can cause the whole system to behave differently each time it is run.

3. **Concurrent Operations:** If there are concurrent operations happening within whole the system that aren't strictly sequenced, small differences in timing or ordering of operations can lead to different outcomes.

4. **Dynamic Rules:** If the rules governing reactive relationships change over time or based on certain conditions, this can introduce non-determinism. 

However, it is important to note that even fully deterministic systems can exhibit nonlinear dynamic behavior, or 'sensitivity to initial conditions'. Nested complex systems, recursively self-similar or not, are inherently prone to this phenomenon, since a small change at one level can lead to unpredictable effects at other levels (e.g. "the butterfly effect"). And similarly, even if the rules governing reactive event relationships are deterministic, their overall behavior can be chaotic.

# Time 

Rather than adhering to a strictly deterministic sequence of events, Rocketship operates by instantiating and de-instantiating, as well as changing and evolving, various deterministic and non-deterministic reactive event relationships over time. In other words, time in Rocketship is dynamically relative to the state of the whole system, rather than being a constant, linear progression.

Understanding the temporality of events involved in a reactive event relationship is critical for realizing how that relationship will unfold. Events in Rocketship do exist within time, but can occur at a single 'moment' ('instantaneous events') or span over a period of time ('extended-duration events'). 

Emitters that emit single, isolated pulses, such as a button press or a threshold being reached, are instantaneous events. On the other hand, Emitters that constantly stream pulse values, such as the playhead position of a timeline or the spatial tracking data of an actor, are considered extended-duration events. Although each discrete pulse could technically be considered an instantaneous event, taken together they form an extended-duration event. Similarly, an instantaneous Action accomplishes its task immediately, whereas an extended-duration Action inherently takes time to complete.

These two kinds of events reflect different kinds of interactions. Instantaneous events often signify direct, one-time interactions, while extended-duration events typically represent ongoing states or processes.

==Time itself can also be an **Emitter**.==
## Event Ordering, Concurrency, and Delay

Depending on the reactive event relationships that have been set up, the order in which events occur can have a significant impact on the way those relationships unfold and affect each other. Moreover, events can occur concurrently, or overlap in duration, leading to complex unpredictable interactions and potential race conditions. It may be necessary to implement logic that prioritizes certain events and handles potential conflicts or ambiguities.

Reactive event relationships in Rocketship are realtime, meaning there is no perceptible latency between cause and effect; however, in certain situations it may be desirable to precisely control the delay between receiving the pulse of an Emitter and sending the bound Action/Bundle. Delay can also be conditional, meaning that a received pulse 'arms' the Action/Bundle, but it is not sent until other conditions are met.
## Recursion and Self-Similarity

Many of the concepts discussed so far may be further explored by integrating the notions of recursion and self-similarity, two distinct but related principles. Complex systems can be nested infinitely within each other, and those systems can exhibit varying degrees of recursion across scale. We can also observe self-similarity in the patterns of relationships themselves. Combining these two aspects, we may even begin to consider reactive event relationships which embody relational patterns that extend across complex systems at multiple recursive levels.

Recursive or self-similar patterns can be observed in both deterministic and chaotic systems. In deterministic systems these patterns unfold predictably, while in chaotic systems they may unfold unpredictably.

Finally, when chaotic systems display recursion or self-similarity, this can result in what's known as "fractal chaos". This is when chaotic behavior, though seemingly random at smaller scales, reveals self-similar patterns when viewed across larger scales or over longer timespans.

# 4. Complexity

In the context of Rocketship, the notion of complexity exists at many levels:

1. **System Complexity:** This refers to the complexity of ==the entire network of subsystems== (i.e., the "whole system"), and is influenced by the number, type, and diversity of mediums of the various subsystems.

2. **Subsystem Complexity:** This refers to the complexity of ==each individual subsystem== within the network. It is influenced by factors such as the internal logic and structure of the subsystem, as well as the number and diversity of **Emitters** and **Actions** it registers.

3. **Reactive Event Relationship Complexity:** This refers to the complexity of ==a specific reactive event relationship== within the Rocketship system. Factors influencing this kind of complexity include:

	- **Emitter Complexity:** The variety of Emitter types that can initiate a reactive relationship. A system where a multitude of different Emitters can trigger reactions has a higher Emitter complexity.
    
	- **Action Complexity:** The variety and intricacy of potential Actions in response to a given Emitter. A system that can generate a wide array of Actions in response to an Emitter exhibits high Action complexity.
    
	- **Algorithmic Complexity:** The complexity of the rules or logic that determine the Action in response to an Emitter. If the set of rules governing Actions is intricate or has many conditional statements, the system displays high rule complexity.
	
	- **Relational Complexity:** The complexity determined by the type and variety of a reactive event relationship.

4. **Dynamic Complexity:** This type of complexity pertains to ==the unpredictability and changeability of a reactive event relationship that evolves over time==. Dynamic complexity can manifest in the form of cyclical changes, trends, or abrupt shifts in the reactive event relationship's dynamic. A reactive event relationship that adapts over time to user behavior or external conditions would demonstrate higher dynamic complexity.
    
5. **Informational Complexity:** Informational complexity in a reactive event relationship refers to ==the quantity and diversity of data processed by the relationship==. The more varied and voluminous the information considered, the higher the informational complexity.

It's also worth considering how different levels of complexity interact with one another. In a directly proportional manner, an increase in Subsystem Complexity would lead to an increase in System Complexity; however, a system could have high complexity due to a multitude of subsystems, each with their own multitude of Emitters and Actions, yet the reactive event relationships themselves might be simple and straightforward; and conversely, a system might consist of only a few subsystems, but if the reactive event relationships within it are highly complex, it could lead to a significant amount of complexity in terms of understanding or predicting system behavior.

In addition, there exists an important distinction between **Potential Complexity** and **Realized Complexity:**

- **Potential Complexity:** This refers to ==the theoretical maximum complexity that the system could generate==. It is dictated by the system's configuration: the number and type of Emitters and Actions, the complexity of the rules governing their interaction, the number of subsystems involved, and so on. However, because the activation of a reactive event relationship depends on the occurrence of certain events (which may be probabilistic or dependent on external inputs), not all of this complexity might be observed in reality.
    
- **Realized Complexity:** This refers to ==the complexity that is actually observed during the operation of the system==. It depends on which events occur, which reactive event relationships are activated, and the specific ways in which these relationships interact. It may be substantially lower than the potential complexity if only a subset of the possible events occur, or if the events that do occur activate relatively simple reactive event relationships.

Types of reactive event relationships are varyingly complex, and each relationship may also simultaneously be of multiple types. Considering these factors introduces the even higher-order concept of **'Relational Complexity'**. For example, a causal relationship is the least complex kind of relationship, whereas a hierarchical relationship can be as complex as the hierarchical structure itself determines; and a relationship that is simultaneously co-evolutionary *and* multi-directional expresses a greater degree of complexity than would a relationship that is solely either co-evolutionary *or* multi-directional.

***

We might also ask: To what extent is the complexity of a reactive event relationship perceptible to an observer? The notion of **'Perceptual Complexity'** is determined by a number of factors:

1. **Awareness:** This refers to the degree to which an observer is aware of a reactive event relationship, i.e., whether they can identify the existence of a link between an Emitter and an Action. ==From the perspective of a **Rocketship Operator**, conscious manipulation of the spectrum of Awareness, i.e., conscious awareness of Awareness, is a crucial aspect of creating reactive event relationships.== This Awareness may be influenced by:
    
    - **Transparency:** How clear is the link between the Emitter and the Action? In some cases, an Action might follow an Emitter so closely that the relationship is immediately obvious. In other cases, there may be a delay, or the relationship may be obscured by other factors, making it less obvious.
        
    - **Familiarity:** How familiar is the observer with the underlying system logic? A system operator would inherently understand the relationships they have created, whereas an outside observer would not.
        
2. **Comprehension:** This refers to the observer's ability to understand the underlying logic or rules governing a reactive event relationship. They might be aware of a reactive event relationship, but not understand why it occurs or what governs it. This might be influenced by:
    
    - **Intrinsic complexity:** How complex are the underlying rules or logic? If the relationship between an Emitter and an Action is governed by intricate or multi-step rules, it may be more difficult for an observer to interpret.
    
    - **Knowledge Gap:** This refers to the difference between an observer's existing understanding of the system, and the understanding required to fully grasp the logic or rules that govern the reactive event relationship. This gap could exist due to lack of exposure, limited information, or other reasons that hinder the observer's comprehension of the underlying mechanisms of the system. The larger the gap, the more challenging it may be for the observer to interpret the relationship, thereby increasing its Perceptual Complexity.

In summary, the complexity of a Rocketship-powered system manifests across multiple dimensions. System and Subsystem Complexity look at the breadth and depth of the reactive elements present, while Reactive Event Relationship Complexity, Dynamic Complexity, and Informational Complexity focus on the nature of the interactions and transformations that occur within the system. Furthermore, the distinctions between Potential and Realized Complexity help delineate between the theoretical and realistic manifestations of complexity. Meanwhile, Perceptual Complexity provides a lens through which to consider the observer's understanding and awareness of a system's complexity. These facets of complexity are far from isolated, often intersecting and interacting with each other, and contribute to the emergent behavior of a Rocketship-powered system. By gaining an understanding of these different dimensions of complexity, a **Rocketship Operator** is better equipped to analyze, design, and manage such systems with a fuller awareness of their possible behaviors, limitations, and opportunities.

# 5. Design Patterns and Principles

Consider a two-subsystem setup involving Ableton Live and Unreal Engine. To design a reactive event relationship following the constructivist approach, we begin by defining the events that will be involved and translating them into Rocketship's syntax.

From Ableton, we would like to consider playback state changes as events. The transport **Target** surfaces Ableton's playback state through an **Emitter** that emits a **Pulse** whenever the playback state changes. The **Pulse** data is binary; Ableton can either be 'playing' or 'not playing'.

From Unreal, we would like to consider the state changes of the color of a light as events. The light's **Target** component surfaces an **Action** to Rocketship which sets the color of the light. The **Action** data are continuous RGB values.

We can instantiate a basic relationship between these two events such that a change in Ableton's playback state leads to a change in Unreal's light color state. (This relationship would be classified as both Causal and Cross-Domain.) However, the relationship requires a rule and algorithm to handle the cross-domain interaction, since the data types of the **Pulses** (binary) and the **Actions** (continuous RGB) are dissimilar. The rule might state that a **Pulse** triggers the RGB values to be set to random values; or, that the RGB values be set to pre-defined values, for example 'green' when Ableton is playing and 'red' when Ableton is not playing. The algorithm carries out the rule, and is implemented in Unreal's event graph by inserting additional math and/or logic nodes between the 'Rocketship **Action**'' node and the 'set light color' node. It would also be possible to instead implement the data transformation algorithm in Rocketship's node graph, such that Unreal receives **Action** data already in RGB values.



# 6. Relationships Between Relationships