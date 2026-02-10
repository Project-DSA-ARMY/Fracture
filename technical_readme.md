# 🛠 PARADOX LOG – Technical Overview

---

## Project Type

- **Game Type:** Text-Based RPG
- **Platform:** Mobile (Android / iOS)
- **UI Style:** Scroll-based text UI
- **Persistence:** Local save + state tracking

---

## Architecture Overview

The game is built around a **state-driven narrative engine**.

### Core Systems

- Act Manager
- Choice Resolver
- Timeline State Tracker
- Save/Load System
- Dialogue Engine
- Ending Resolver

---

## State Management

Global state variables include:

- `tyrant_index`
- `timeline_stability`
- `self_trust`
- `current_act`
- `past_decision_log`
- `future_intervention_log`

These values persist across acts and determine:
- Dialogue availability
- Event triggers
- Endings

---

## Acts & Flow Control

Each act:
- Loads a predefined narrative module
- Reads global state
- Presents branching choices
- Writes back updated values

Acts are **not replayed linearly** — some content unlocks only if conditions are met.

---

## Save System

- Auto-save after major decisions
- Save slots store:
  - Act number
  - All global variables
  - Narrative flags
- New Game+ resets world but preserves meta-flags

---

## Choice Resolution

Each choice contains:
- Text
- Requirements (state checks)
- Effects (state mutations)
- Optional hidden effects

Choices may:
- Increase or decrease Tyrant Index
- Stabilize or fracture the timeline
- Affect future availability of tools

---

## Tools & Equipment System

Weapons, armor, and items are **narrative modifiers**, not numeric stats.

They affect:
- Available dialogue options
- Choice previews
- Anomaly interactions
- Fail-state prevention

---

## UI Considerations (Mobile)

- Large tap targets
- Minimal animations
- Fast text rendering
- Scroll-friendly layouts
- Interrupt-safe saving

---

## Error Handling

- Soft-lock prevention via fallback choices
- Timeline recovery nodes
- Forced stabilization events if instability exceeds limits

---

## Future Expansion Ready

- DLC acts
- New timeline branches
- Additional endings
- Accessibility modes
