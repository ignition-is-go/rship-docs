# Rship-StreamDeck

The StreamDeck presents a very straightforward Rocketship Executor. 

While there are many variants of the device, its sidecar application provides an easy entry point via plugins.

After installing the Rocketship Plugin into the StreamDeck software, you can map Rocketship-enabled items onto the StreamDeck interface just the same as anything else.

The 'Rocketship Status' item is used to visualize and control connection state with Rocketship.

The 'Rocketship Target' item creates a Target when dragged onto the StreamDeck interface. The Target has various Emitters that send Pulses whenever the state of the button/dial/ changes.

## Targets, Emitters, and Actions

- Targets: Buttons/Dials/Touchscreen
  - Emitters:
    - On Pressed
  - Actions:
    - Set Icon
    - Set Text
