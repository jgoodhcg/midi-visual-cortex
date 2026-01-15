# Foundation: Hello World to Sound

## Work Unit Summary
- Status: active
- Problem / intent: Establish the basic project structure and prove out the core technical stack (Bevy + midir + oxisynth) before building features.
- Constraints: macOS + Linux support. Pure Rust dependencies only.
- Proposed approach: Incremental milestones, each building on the last.
- Open questions: None currently.

## Milestones

### M0: Bevy Hello World
- Cargo project initialized with Bevy dependency
- Window opens with title "MIDI Visual Cortex"
- Black background
- Exits cleanly

### M1: Green Circle
- Render a green circle centered on screen
- Proves Bevy 2D rendering works

### M2: MIDI Input → Visual Feedback
- Add midir dependency
- List available MIDI devices on startup (log to console)
- Connect to first available MIDI input
- On note-on: circle pulses (scale up briefly)
- On note-off: circle returns to normal

### M3: SoundFont Playback
- Add oxisynth dependency
- Load a test SF2 file from disk
- On MIDI note-on: trigger sound via oxisynth
- On MIDI note-off: release note
- Audio output via cpal or rodio

## Notes

This unit is complete when you can:
1. Plug in a MIDI controller
2. See visual feedback when playing
3. Hear sound from a SoundFont

No recording, no piano roll, no UI yet. Just the proof that the stack works.
