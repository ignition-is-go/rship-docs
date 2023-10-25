# Rules and Algorithms

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

