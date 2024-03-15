# Ableton Live

Ableton Live integrates with Rocketship using a Max for Live device and a sidecar application in tandem.

The Max for Live Device can be added to any track in the set, and recursively iterates through the Live Object Model to surface the Targets, Actions, and Emitters of the live set.

The sidecar application runs separately and bridges the connection between Ableton Live and Rocketship.

## Installation

**Rship Device**

Download the 'rship' M4L device and add it to any track in the live set.

**Sidecar App**

Download the 'Rship-Ableton' sidecar app and run it. Enter the address and port of a Rocketship server and connect.

# Targets, Actions, and Emitters

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
