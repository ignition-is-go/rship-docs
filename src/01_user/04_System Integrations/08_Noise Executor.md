# Noise Executor

The noise executor runs on the Rocketship server and publishes some Targets and Emitters that are always available for use. Generally speaking, the purpose of the noise executor is to test out bindings for a subsystem without needing to set up and involve a whole other subsystem. 

Its Emitters are broken up into different categories which represent the kinds of Emitters that would be published by real executors:

- Raw Data
    - Pulse Rate
        - Continuous data stream
        - Period
        - Sporadic
    - Data Type
        - Strings (?)
        - Scalars
        - Vectors
        - Complex structured (e.g. JSON)
- Spatial Data
    - Location tracking
    - Region density
    - Object distance
    - Path tracing
    - Pose/Gesture
    - Orientation
- Audio Data
    - Frequency
    - Amplitude
    - Beat detection
- Sensor Data
    - 

