## Spirit Island Randomizer v4.2.0 — First Production Release

A standalone Windows application for generating randomised Spirit Island game setups. No Python or other software required — just download, extract, and run.

---

### Features

**Randomizer**
- Generate combos for 1–6 players, drawing from all six expansions (Base Game, Branch & Claw, Jagged Earth, Nature Incarnate, Feather & Flame, Horizons of Spirit Island)
- Full Aspects support — each base-spirit family produces at most one result (base spirit or one of its aspects, never both)
- Optional additional board unbound to any spirit
- Optional Adversary and Scenario selection
- Optional strict board compatibility checking

**Selection control**
- Tristate checkboxes for every item: **unchecked** (exclude) · **checked** (include in pool) · **forced/red** (guaranteed in every result)
- Forced state now available for Spirits, Aspects, Boards, Adversaries, and Scenarios
- Right-click a checkbox to cycle states in reverse
- Quick-select buttons: Base Only · Aspects Only · Select All · Deselect All

**Launch integration**
- Generates Handelabra-compliant Spirit Island Digital launch URLs
- Web launch (play.spiritislanddigital.com) or Steam launch — toggle with one checkbox
- One-click Launch button opens the generated combo directly in the game

**Persistence**
- All checkbox selections saved automatically to `user_data/selection_state.json`
- App settings (window size/position, spirit count, launch preference, board compatibility) saved to `user_data/settings_state.json`
- Everything is restored exactly as you left it on next launch

---

### Installation

> **Download both `.zip` parts below, place them in the same folder, then open `SIRPYv4-v4.2.0-windows.zip.001` with 7-Zip, WinRAR, or the Windows 11 built-in extractor.**

1. Download **`SIRPYv4-v4.2.0-windows.zip.001`** and **`SIRPYv4-v4.2.0-windows.zip.002`**
2. Extract — open `.zip.001` and extract to a folder of your choice
3. Run **`SIRPYv4.exe`**

**Requires Windows 10 or Windows 11 (64-bit). No Python or other dependencies.**

---

### Notes

- This is a personal/fan tool with no affiliation with Greater Than Games or Handelabra
- Spirit Island is © Greater Than Games
