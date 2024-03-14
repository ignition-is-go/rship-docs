# Installation

Rocketship can receive **Emitters** from, and take **Actions** on, Ableton Live. There are a few different pieces of software that work together to make this possible:

### Ableton

- You MUST name your scenes in Ableton in order for them to show up in Rocketship

### RshipAbletonControlSurface

The Ableton Live API is partially exposed by a custom control surface script. Download the script folder and place it in the correct directory according to your OS.

Windows: "C:/Users/[User]/Documents/Ableton/User Library/Remote Scripts/"
Mac: "/Users/[User]/Music/Ableton/User Library/Remote Scripts"

Restart or open Ableton and navigate to Options -> Preferences -> Link and add the Rship control surface.

### Max for Live

Other elements of the Ableton Live API that are not exposed by AbletonJS, are instead exposed by a Max for Live device. The device must be added to every track you wish to observe/control from Rocketship.

### The Sidecar App

Lastly, an Electron app running alongside Ableton Live handles the connection with Rocketship, and also provides connection status indicators and an event log.

# Ableton Targets, Actions, and Emitters

- Targets:
	- Song:
		- Emitters:
			- is_playing
	- Master Track:
		- Emitters (as device params):
			- volume
			- panning
			- cue_volume
			- crossfader
			- song_tempo
		- Actions:
			- set volume
			- set panning
			- set cue_volume
			- set crossfader
			- set song_tempo
	- Track:
		- Emitters:
			- arm
	- Mixer Device (track):
		- Emitters (as device params):
			- volume
			- panning
			- track_activator (mute/unmute)
		- Actions
			- set volume
			- set panning
			- set track_activator
	- Chain:
		- Emitters (supported by rocketship on mac, currently timing out on pc)
			- solo
			- mute
			- muted_via_solo
			- name
			- is_auto_colored
			- color
			- cell-fired​
		- Emitters, m4L Drum Cell emitter:
			- solo
			- mute (currently crashing ableton on quit/project change, reported to cycling 74, ready to implement on issue resolution)
			- muted_via_solo
			- name
			- is_auto_colored
			- color
			- cell-fired
		- Actions, m4L Drum Cell emitter:
			- set solo
			- set volume
			- set panning
	- Device Parameter
		- value
		- Actions:
			- set_value
	- Master:
		- is_playing
	- Clip:
		- Emitters:
			- Playing position 
	- Clipslot
		- Emitters:
			- playing_slot_index
			- play_started
			- play_stopped
	- CuePoint
		- fired
