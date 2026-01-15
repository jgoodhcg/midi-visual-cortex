# Music Theory Analysis

## Work Unit Summary
- Status: idea
- Problem / intent: Help users understand what they're playing with note names, chord detection, and scale highlighting.
- Constraints: Analysis is derived/non-destructive. Never modifies source data. Best-effort heuristics, not perfect theory.
- Proposed approach: Real-time analysis systems that annotate the piano roll view.
- Open questions: How to handle ambiguous chords? Show multiple interpretations or pick most likely?

## Scope

### Note Labels
- Display note name + octave (C3, D#4, etc.)
- Toggle on/off

### Chord Detection
- Analyze notes sounding simultaneously (or within time window)
- Identify chord name (Cmaj, Am7, G7, etc.)
- Display above piano roll at each time slice
- Best-effort heuristic (not exhaustive music theory)

### Scale Highlighting
- User selects key + mode (C major, A minor, D dorian, etc.)
- Highlight scale tones on piano roll grid
- Color-code: chord tones vs passing tones vs out-of-key

### Interval Visualization
- Show intervals between selected notes
- Helpful for learning harmony

### Grid + Timing
- Beat/bar grid lines
- Swing visualization (if tempo has swing)

## Notes

This is the "visual learning" aspect of the tool. Should help users build musical intuition without being a theory textbook. Keep it simple and non-intrusive.
