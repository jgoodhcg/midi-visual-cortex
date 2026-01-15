# MPE Support

## Work Unit Summary
- Status: idea
- Problem / intent: Support MIDI Polyphonic Expression (MPE) for expressive controllers like Artiphon Chorda, Roli Seaboard, Linnstrument.
- Constraints: Should be additive, not break standard MIDI workflow. Optional feature.
- Proposed approach: Extend Note struct with optional expression curves. Record per-note pitch bend, pressure, slide during MPE input.
- Open questions: How to visualize expression data in piano roll? Separate lanes or overlays?

## Scope

### Data Model Changes
- Note struct gains optional fields:
  - pitch_bend_curve: Vec<(time, value)>
  - pressure_curve: Vec<(time, value)>
  - slide_curve: Vec<(time, value)>

### MPE Recording
- Detect MPE mode (multiple channels for notes)
- Track which channel corresponds to which active note
- Capture CC74 (slide), channel pressure, pitch bend per-note

### MPE Playback
- Replay expression curves during playback
- Route each note to appropriate channel for expression

### Visualization (stretch)
- Show expression data in piano roll
- Pitch bend as vertical curve on note
- Pressure/slide as color or thickness

## Notes

MPE makes expressive controllers shine. Without it, you lose the per-note expression that makes instruments like Chorda special. But it's an enhancement, not core functionality.
