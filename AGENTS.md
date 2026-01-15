# Shared Agent Guidelines

This is the source of truth for all AI agents (Claude, Gemini, etc.) working on this project.

## Project Overview

**Visual MIDI Jam Sketchpad** - A MIDI-first sketching tool for jamming with a MIDI controller, visually exploring notes/chords/scales, looping riffs across multiple tracks, monitoring sound via SoundFonts, and exporting clean MIDI to full DAWs.

This tool is for **musical intuition + fast iteration**, not final production.

## Workflow Preferences
- **One Step at a Time:** Perform a single logical task, then stop and ask for validation/feedback. Do not chain multiple feature implementations or fixes together.
- **Validation First:** Always reflect on the current state and plan before executing.
- **User Control:**
    - **Never** run dev servers or long-running processes automatically.
    - **Never** run the application without explicit user request.
    - **Never** assume MIDI device state; ask the user to verify if unsure.
- **Roadmap Driven:** Keep the roadmap up-to-date and reference it frequently.
- **Decision Matrices:** Use `.decisions/` folder with matrix-reloaded format for significant technical decisions.

## Development Context
- **Tooling:** Cargo for all Rust tooling; dependencies in `Cargo.toml`.
- **Generated Files:** `target/` directory (build artifacts), not committed.
- **Environment:** No `.env` files expected initially. MIDI devices detected at runtime.

## Tech Stack
- **Language:** Rust (latest stable)
- **Engine / UI:** Bevy (latest stable)
- **MIDI I/O:** `midir`
- **MIDI file export:** `midly`
- **Audio playback:** `oxisynth` (SF2 SoundFont synthesis)
- **Platforms:** macOS + Linux

## Allowed Verification Commands
| Command | Description |
|---------|-------------|
| `cargo check` | Type-check the project without building |
| `cargo build` | Build the project |
| `cargo test` | Run all tests |
| `cargo clippy` | Run linter |
| `cargo fmt --check` | Check code formatting |
| `cargo fmt` | Fix code formatting |

## User-Only Commands
| Command | Description |
|---------|-------------|
| `cargo run` | Run the application |
| `cargo run --release` | Run optimized build |

## Project Structure (will evolve)
```
src/
  main.rs           - Entry point, Bevy app setup
  lib.rs            - Library root (if needed)
  systems/          - Bevy ECS systems
    midi_input.rs   - MIDI input handling
    playback.rs     - Note scheduling and playback
    audio.rs        - SoundFont rendering
    render.rs       - Piano roll visualization
    edit.rs         - Note editing
    analysis.rs     - Chord/scale detection
  components/       - Bevy ECS components
  resources/        - Bevy ECS resources
  events/           - Bevy events
  ui/               - UI components
roadmap/            - Feature planning and requirements
.decisions/         - Decision matrices (matrix-reloaded format)
assets/             - SoundFonts, fonts, sprites (if any)
```

## Non-Goals (Hard Scope Limits)
- No audio waveform tracks
- No effects, mixing, automation
- No plugin hosting (VST/AU)
- No deep sound design UI
- No final audio mastering

If a feature requires a non-MIDI timeline, it is out of scope.

## Code Style Guidelines
- Use `rustfmt` defaults
- Prefer explicit types in public APIs
- Group imports: `std` > external crates > local modules
- Use Bevy's system ordering and scheduling idioms
- Docstrings for public functions
- Tests alongside code or in `tests/` directory

## Data Model (Conceptual)
- **Note:** pitch, velocity, start_time, duration
- **Track:** id, MIDI channel, SoundFont reference, program number, notes
- **Transport:** tempo, playhead, loop_start/end, playing/stopped
- **Session:** tracks, SoundFont registry

## Emergency Recovery
- If the application is started accidentally, stop all agent processes immediately.
- MIDI devices may need to be reconnected after crashes.
