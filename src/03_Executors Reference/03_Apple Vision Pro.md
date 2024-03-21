# Apple Vision Pro

The Apple Vision Pro integrates with Rocketship by running a visionOS app that implements the Swift variant of the Rocketship Executor SDK.

Due to Apple's privacy limitations, an app can only surface tracking and world sensing data if it occupies a 'full space', meaning no other apps are running. Apps are also generally unable to access information about other apps. This prevents us from designing an Executor in the usual way, by running a background process or sidecar that monitors the state of the system and surfaces Targets to Rocketship.

Instead, we create visionOS apps designed with a particular project or experience in mind, and define more explicitly the Target/Action/Emitter structure on a per-app basis.

For research and development purposes, we have created an RshipVisionOS demo app to explore the capabilities of the visionOS SDK, which exposes the following providers through the ARKit library:

- Hand Tracking Provider
    - Provides live transform (position and rotation) data for the fingertips, metacarpal joints, knuckles, wrist, and elbow.
    - Provides gesture recognition for pre-defined poses and gestures.
- World Tracking Provider
    - Provides live transform data for the device, and any pre-defined anchor points in the world space.
- Plane Detection Provider 
    - Provides live transform and mesh data, as well as semantic classification, for any surfaces the device detects.
- Scene Reconstruction Provider
    - Provides live transform and mesh data, as well as semantic classification, for any objects the device detects.

In addition, any SwiftUI component can be made into a Target.

## Installation

> 1. Download the RshipVisionOS app and run it on an Apple Vision Pro
> 2. Navigate to the 'Status' page to enter an address and port and connect to a Rocketship server.
> 3. Navigate to the 'Demo' page to activate the immersive space and begin providing live tracking and world sensing data.

## Targets, Actions, and Emitters

| Targets                 | Emitters                                    | Actions |
|-------------------------|---------------------------------------------|---------|
| **Device**              | - Transform data                            |         |
| **Left Hand**           | - Fingertips transform data                 |         |
|                         | - Metacarpal transform data                 |         |
|                         | - Knuckle transform data                    |         |
|                         | - Wrist transform data                      |         |
|                         | - Elbow transform data                      |         |
| **Right Hand**          | - Fingertips transform data                 |         |
|                         | - Metacarpal transform data                 |         |
|                         | - Knuckle transform data                    |         |
|                         | - Wrist transform data                      |         |
|                         | - Elbow transform data                      |         |
| **Gesture Recognition** | - Left hand gesturing                       |         |
|                         | - Right hand gesturing                      |         |
|                         | - Both hands gesturing                      |         |