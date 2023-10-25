# Properties of Reactive Event Relationships

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

