# Installation

Rocketship can receive **Emitters** from, and take **Actions** on, Ableton Live. There are a few different pieces of software that work together to make this possible:

### Ableton

- You MUST name your scenes in Ableton in order for them to show up in Rocketship

### RshipAbletonControlSurface

The Ableton Live API is partially exposed by a custom control surface script. Download the script folder and place it in the correct directory according to your OS.

Windows: C:/Users/[User]/Documents/Ableton/User Library/Remote Scripts/
Mac: 

Restart or open Ableton and navigate to Options -> Preferences and add the Rship control surface.

### Max for Live

Other elements of the Ableton Live API that are not exposed by AbletonJS, are instead exposed by a Max for Live device. The device must be added to every track you wish to observe/control from Rocketship.

==consult Matt to determine what works in the M4L device==

### The Sidecar App

Lastly, an Electron app running alongside Ableton Live handles the connection with Rocketship, and also provides connection status indicators and an event log.

