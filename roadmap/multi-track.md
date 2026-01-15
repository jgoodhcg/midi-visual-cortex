# Multi-Track Support

## Work Unit Summary
- Status: idea
- Problem / intent: Allow layering multiple MIDI tracks, each with its own instrument/SoundFont.
- Constraints: Unlimited tracks. Each track has one MIDI channel and one SoundFont program.
- Proposed approach: Track list UI, per-track SoundFont/program selection, track mute/solo.
- Open questions: How to handle MIDI channel routing when recording? Auto-assign or user-selected?

## Scope

### Track Management
- Create new track
- Delete track
- Reorder tracks
- Track naming

### Per-Track Settings
- SoundFont selection (from indexed library)
- Program/instrument selection
- MIDI channel assignment
- Mute / solo

### Recording Target
- Select which track receives MIDI input
- Visual indicator for armed/recording track

### SoundFont Library
- User specifies directories to scan
- Index available SF2 files
- Browse and preview sounds

## Notes

Multi-track is what makes this a "jam sketchpad" vs just a MIDI monitor. Essential for layering drums, bass, melody, etc.
