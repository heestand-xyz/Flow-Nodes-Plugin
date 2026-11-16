# Realtime nodes

Each linked JSON file contains a parent group. Select the entry in `nodes` with the exact listed `typePath` for ports and properties. Prefer visible replacements for new flows.

- **Communication / Connectivity** — Free. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:connectivity`. Connectivity of WiFi and cellular network status with IP address information.
- **Communication / MIDI Receive** — Free. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:midiReceive`. Receive MIDI notes.
- **Communication / MIDI Receive CC** — Free. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:midiReceiveCC`. Receive MIDI control changes.
- **Communication / MIDI Receive List CC** — Free. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:midiReceiveListCC`. Receive a list of MIDI control changes.
- **Communication / MIDI Transmit** — Pro. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:midiTransmit`. Send MIDI notes.
- **Communication / MIDI Transmit CC** — Pro. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:midiTransmitCC`. Send MIDI control changes.
- **Communication / NDI Receive** — Free. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:ndiReceive`. Receive realtime graphics on the local network. NDI® is a registered trademark of Vizrt NDI AB.
- **Communication / NDI Transmit** — Pro. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:ndiTransmit`. Send realtime graphics over the local network. NDI® is a registered trademark of Vizrt NDI AB.
- **Communication / OSC Receive** — Free. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:oscReceive`. Receive OSC messages. To see the received value; connect the generic outlet to a relay node with the expected value type.
- **Communication / OSC State** — Pro. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:oscState`. Send and receive OSC messages. To see the received value; connect the generic outlet to a relay node with the expected value type.
- **Communication / OSC Transmit** — Pro. [JSON](../nodes/realtime/communication.json) · `node:realtime:communication:oscTransmit`. Send OSC messages.
- **Home / Light** — Free. [JSON](../nodes/realtime/home.json) · `node:realtime:home:light`. Control a light in a room in your home. Powered by HomeKit.
- **Intent / Action** — Free. [JSON](../nodes/realtime/intent.json) · `node:realtime:intent:action`. Triggers an action when the Flow Nodes "Node Action" intent runs. Use the "Node Action" shortcut with the Action Button on iPhone, or use the "Node Action" intent in the Shortcuts app, or just say "Hey Siri trigger action in ".
- **Intent / Float Input** — Free. [JSON](../nodes/realtime/intent.json) · `node:realtime:intent:floatInput`. Receive a float value when the Flow Nodes Node Float Input Intent runs. Use the intent with the action button on iPhone or the Shortcuts app.
- **Intent / Float Output** — Free. [JSON](../nodes/realtime/intent.json) · `node:realtime:intent:floatOutput`. Send a float value when the Flow Nodes Node Float Output Intent runs. Use the intent with the action button on iPhone or the Shortcuts app.
- **Intent / String Input** — Free. [JSON](../nodes/realtime/intent.json) · `node:realtime:intent:stringInput`. Receive a string value when the Flow Nodes Node String Input Intent runs. Use the intent with the action button on iPhone or the Shortcuts app.
- **Intent / String Output** — Free. [JSON](../nodes/realtime/intent.json) · `node:realtime:intent:stringOutput`. Send a string value when the Flow Nodes Node String Output Intent runs. Use the intent with the action button on iPhone or the Shortcuts app.
- **Modulator / Noise** — Free. [JSON](../nodes/realtime/modulator.json) · `node:realtime:modulator:noise`. Simplex noise.
- **Modulator / Wave** — Free. [JSON](../nodes/realtime/modulator.json) · `node:realtime:modulator:wave`. A low frequency oscillator. A sine wave.
- **Sensor / Accelerometer** — Free. [JSON](../nodes/realtime/sensor.json) · `node:realtime:sensor:accelerometer`. Device accelerometer updates.
- **Sensor / Compass** — Free. [JSON](../nodes/realtime/sensor.json) · `node:realtime:sensor:compass`. Heading of the current device.
- **Sensor / Face Tracking** — Free. [JSON](../nodes/realtime/sensor.json) · `node:realtime:sensor:faceTracking`. Track your face with the true depth camera. Get blend shapes, from mouth, eye and more.
- **Sensor / Game Controller** — Free; deprecated; replacement node:realtime:sensor:gameController2. [JSON](../nodes/realtime/sensor.json) · `node:realtime:sensor:gameController`. Receive signals from a bluetooth connected game controller.
- **Sensor / Game Controller** — Pro. [JSON](../nodes/realtime/sensor.json) · `node:realtime:sensor:gameController2`. Choose a connected game controller device and read each controller element from its own outlet.
- **Sensor / Gyroscope** — Free. [JSON](../nodes/realtime/sensor.json) · `node:realtime:sensor:gyroscope`. Device gyroscope updates.
- **Sensor / Haptics** — Free. [JSON](../nodes/realtime/sensor.json) · `node:realtime:sensor:haptics`. Trigger a haptic feedback on the device.
- **Sensor / Location** — Free. [JSON](../nodes/realtime/sensor.json) · `node:realtime:sensor:location`. Geo location of the current device.
- **Sensor / Microphone** — Free. [JSON](../nodes/realtime/sensor.json) · `node:realtime:sensor:microphone`. Microphone audio levels.
