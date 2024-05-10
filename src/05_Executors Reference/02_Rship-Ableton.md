# Rship-Ableton

Ableton Live integrates with Rocketship using a Max for Live device and a sidecar application called 'Rship-Ableton'.

The Max for Live Device can be added to any track in the set, and recursively iterates through the Live Object Model to register the Targets, Actions, and Emitters of the live set with Rocketship.

Rship-Ableton runs separately and bridges the connection between Ableton Live and Rocketship.

## Installation

**rship.amxd**

Download the rship.amxd and add it to any track in the set.

> NOTE: As of Ableton 12, disabling/enabling the M4L device or opening it in the Max editor from Ableton will create multiple instances of the device which fight over the same UDP port. In order to reconnect to the sidecar, you must quit out of Max entirely and restart Ableton.

**Rship-Ableton**

Download the 'Rship-Ableton' sidecar app and run it. Enter the address and port of a Rocketship server and connect.

## Targets, Actions, and Emitters

| Targets          | Emitters                          | Actions                              |
|------------------|-----------------------------------|--------------------------------------|
| **Song**         | - Current song time (in beats)    | - Continue playing                   |
|                  | - Is playing                      | - Jump to next cue                   |
|                  |                                   | - Jump to previous cue               |
|                  |                                   | - Start playing                      |
|                  |                                   | - Stop playing                       |
| **Master Track** | - Output meter left               |                                      |
|                  | - Output meter right              |                                      |
|                  | - Output meter peak level         |                                      |
| **Master Mixer** | - Volume                          | - Set volume                         |
|                  | - Panning                         | - Set panning                        |
| **Track**        | - Output meter left               |                                      |
|                  | - Output meter right              |                                      |
|                  | - Output meter peak level         |                                      |
| **Mixer Device** | - Volume                          | - Set volume                         |
|                  | - Panning                         | - Set panning                        |
|                  | - Track activation (mute/unmute)  | - Set track activation (mute/unmute) |
| **Device**       | - Is active                       |                                      |
| **Device Parameter** | - Value                       | - Set value                          |
| **Clip**         | - Playing position                | - Fire                               |
|                  | - Is playing                      | - Stop                               |
|                  | - Is triggered                    |                                      |
| **Cue Point**    |                                   | - Jump                               |

For more information on available Targets in Ableton, please consult the [Live Object Model](https://docs.cycling74.com/max8/vignettes/live_object_model)