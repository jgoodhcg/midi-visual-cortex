# MIDI Export

## Work Unit Summary
- Status: idea
- Problem / intent: Export session as a standard MIDI file (.mid) that can be imported into any DAW.
- Constraints: Must produce valid Format 1 MIDI files. One track per sequencer track.
- Proposed approach: Use midly crate to write MIDI files.
- Open questions: Include tempo changes? Export loop region only or full session?

## Scope

### Basic Export
- Export all tracks to single .mid file
- Format 1 (multi-track, synchronized)
- Preserve tempo
- Preserve note timing, pitch, velocity, duration

### Export Options
- Export full session vs loop region only
- File save dialog

### Validation
- Exported files should open correctly in:
  - Logic Pro
  - Ableton Live
  - GarageBand
  - Reaper
  - Any standard DAW

## Notes

This is the escape hatch. The whole point is to sketch ideas here, then finish them in a full DAW. Export must be reliable and clean.
