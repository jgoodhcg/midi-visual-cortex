# Sequencer Core: Piano Roll + Recording + Playback

## Work Unit Summary
- Status: idea
- Problem / intent: Enable recording MIDI input, visualizing it on a piano roll, and playing it back in a loop.
- Constraints: MIDI-only timeline. No audio waveforms.
- Proposed approach: Build piano roll visualization first, then add recording, then playback with loop region.
- Open questions: What UI framework/approach for the piano roll? Pure Bevy 2D or egui integration?

## Scope

### Piano Roll Visualization
- Time on X axis, pitch on Y axis
- Notes rendered as rectangles
- Playhead indicator
- Grid lines for beats/bars
- Scroll and zoom

### Recording
- Arm track for recording
- Capture note-on/off with timestamps
- Convert MIDI events to Note entities (pitch, velocity, start, duration)
- Notes appear on piano roll as recorded

### Playback
- Transport controls: play, stop, loop
- Loop region (start/end markers)
- Schedule note-on/off based on playhead position
- Sync playhead to tempo

### Light Editing
- Select notes
- Move notes (drag)
- Trim note duration
- Delete notes
- Quantize to grid (snap presets: 1/4, 1/8, 1/16)

## Notes

This is the core of the "jam sketchpad" experience. Should feel immediate and responsive.
