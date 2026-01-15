# Session Persistence

## Work Unit Summary
- Status: idea
- Problem / intent: Save and load sessions so users can return to work in progress.
- Constraints: Format should be human-readable if possible. Must preserve all track/note data.
- Proposed approach: JSON or similar serialization format. File extension: .mvc or .json.
- Open questions: Include SoundFont references by path or by name? How to handle missing SoundFonts on load?

## Scope

### Save Session
- Serialize all tracks, notes, transport settings
- Include SoundFont references (path or identifier)
- Include tempo, loop region
- File save dialog with .mvc extension

### Load Session
- Deserialize and restore full session state
- Handle missing SoundFonts gracefully (warn user, use fallback)
- File open dialog

### Auto-save (stretch)
- Periodic auto-save to recovery file
- Restore from auto-save on crash recovery

## Notes

Essential for any creative tool. Users need to be able to stop and resume.
