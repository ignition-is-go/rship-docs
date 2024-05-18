# Rship-Ableton

Ableton Live integrates with Rocketship using a Max for Live device and a sidecar application called 'Rship-Ableton'.

The Max for Live Device can be added to any track in the set, and recursively iterates through the Live Object Model to register the Targets, Actions, and Emitters of the live set with Rocketship.

Rship-Ableton runs separately and bridges the connection between Ableton Live and Rocketship.

## Installation

**rship.amxd**

Download the rship.amxd and add it to any track in the set.

> NOTE: As of Ableton 12, disabling the M4L device, or opening the device in the Max editor, will disconnect Ableton from Rocketship.

**Rship-Ableton**

Download the 'Rship-Ableton' sidecar app and run it. Enter the address and port of a Rocketship server and connect.

## Targets, Actions, and Emitters

> NOTE: The term 'float, beats' refers to a float value in Ableton's internal measure-beat timing system, where each whole number corresponds to one beat.

- Targets: Song
  - Emitters:
    - Is playing (boolean)
    - Song Tempo (float, BPM)
    - Current song time (float, beats)
  - Actions:
    - Start playing
    - Continue playing
    - Stop playing
    - Set Song Tempo (BPM, 20-999)

- Targets: Locators (Cue Points)
  - Emitters:
    - Time (float, beats)
  - Actions:
    - Jump

- Targets: Master Track
  - Emitters:
    - Output meter left (float)
    - Output meter right
    - Output meter peak level

- Targets: Master Mixer
  - Emitters:
    - Volume
    - Panning
  - Actions:
    - Set volume
    - Set panning

- Targets: Track
  - Emitters:
    - Output meter left
    - Output meter right
    - Output meter peak level

- Targets: Mixer Device
  - Emitters:
    - Volume
    - Panning
    - Track activation (mute/unmute)
  - Actions:
    - Set volume
    - Set panning
    - Set track activation (mute/unmute)

- Targets: Device
  - Emitters:
    - Is active

- Targets: Device Parameter
  - Emitters:
    - Value
  - Actions:
    - Set value

- Targets: Clip
  - Emitters:
    - Playing position
    - Is playing
    - Is triggered
  - Actions:
    - Fire
    - Stop

- Targets: Cue Point
  - Actions:
    - Jump
