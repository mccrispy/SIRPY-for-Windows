# Spirit Island Randomizer

[![Version](https://img.shields.io/badge/version-4.4.0-blue)](CHANGELOG.md)
[![License: CC BY-NC-ND 4.0](https://img.shields.io/badge/License-CC%20BY--NC--ND%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-nd/4.0/)

A Windows desktop app that generates random Spirit Island game combinations and launches them directly in Spirit Island Digital.

---

## Requirements

- Windows 10 or 11
- No Python or additional software required

---

## Installation

1. Download **all** release archive parts (`.zip.001`, `.zip.002`, …) into the same folder
2. Right-click `.zip.001` and choose **Extract here** — or open it with 7-Zip and choose *Extract to…*
3. Open the extracted `SIRPYv4` folder
4. Run **`SIRPYv4.exe`**

> The first launch may take a few extra seconds as Windows verifies the files. Subsequent launches are fast.

---

## Quick Start

1. Open the **Spirit Pool** tab and check the spirits you want to include
2. Set the **spirit count** slider to how many spirits you want in the game setup
3. Click **Generate**
4. Review the result in the results panel
5. Click **Launch** to open the game setup in Spirit Island Digital

---

## Usage

### Choosing Spirits

The **Spirit Pool** tab shows all spirits in a collapsible tree. Each base spirit can be expanded to reveal its aspects.

- **Tristate checkboxes** control whether an item is included — see [Checkbox States](#checkbox-states) below
- **Base Only** / **Aspects Only** — bulk-select only base spirits or only aspects in one click.
- **Select All** / **Deselect All** — check or uncheck every item at once
- **Expansion filter** — dropdown panel to filter the list to spirits from specific expansions
- **Complexity filter** — dropdown panel to filter by spirit complexity (Low / Medium / High / Very High)
- **Name filter** — dropdown panel with a live text search to find spirits by name
- Each filter has an on/off toggle (click the button) and its own **Clear** button; **Clear All Filters** resets all three at once. Note that when a filter is active, the bulk operations work on the *filtered subset*

One spirit *or* one of its aspects will appear in any given game setup — never both at the same time.

---

### Boards, Adversaries & Scenarios

The **Other Pools** tab has three columns: Boards, Adversaries, and Scenarios.

Each column has its own **Select All** / **Deselect All** buttons and uses the same tristate checkboxes as the spirit list.

---

### Control Panel

The control panel on the right side of the main window contains:

| Control                                                     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| ----------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Spirit count** slider                                     | How many spirits to include in the generated game setup (1–6)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Branch & Claw** / **Jagged Earth** / **Nature Incarnate** | Toggle each expansion on or off (this affects the available Spirits, Events, Fear, and Powers)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Include Additional Board**                                | Add one extra random board not assigned to any spirit                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| **Strict Board Compatibility**                              | Only generate board combinations that avoid very swingy setups as a result of concentrating terrains                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Thematic Boards**                                         | Restrict board selection to thematic (named) boards (compass-direction names, fixed arrangement). The layout panel switches to the thematic arrangement diagram for the current player count. If a result is already showing when you toggle this on, the boards are immediately reassigned to the fixed thematic set in compass order; toggling back off restores the original board assignments. If "Include Additional Board" was active and the spirit count is 6, the additional board is temporarily dropped in thematic mode and restored when you switch back. The Board Layout selector is disabled while thematic mode is active. |
| **Board Layout**                                            | Choose how the boards are physically arranged. Pick a named layout (e.g. Coastline, Leaf, Star), select **Random** to let the app choose a valid layout automatically, or leave it on **Standard**. ick the **Preferred** checkbox to save the current selection as the default for this board count — the app will auto-apply it whenever you return to that count.                                                                                                                                                                                                                                                                        |
| **Use Events**                                              | Toggles the "Events" gameplay option. On uses Events, Off uses Command Beasts                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |


---

### Generating a game setup

Click **Generate**. The results panel shows the selected spirits (or aspects), boards, adversary, and scenario for this game setup.

Click **Generate** again at any time to produce a new combination with the same settings.

---

### Launching in Spirit Island Digital

Click **Launch** to open the current game setup in Spirit Island Digital.

- **Web launch** (default) — opens the Handelabra Launch page at play.spiritislanddigital.com.
- **Local Launch** checkbox — directly launches the Steam version of Spirit Island Digital

> Spirit Island Digital must be installed, but the **game must _not_ be running** for Steam launch to work.

---

### Saving & Loading Results

- **Save Result** — saves the current results text to a file (defaults to `Documents\SIRPYv4\`)
- **Load Result** — loads a previously saved result file back into the results panel
- **Copy** — copies the current result text to the clipboard

---

### Profiles

A profile captures all your current selections (spirits, boards, adversaries, scenarios) and settings (expansion toggles, board options, spirit count, etc.) in a single file.

- **Save Setup** — opens a file dialog; save the setup anywhere you like
- **Load Setup** — opens a file dialog; restores all selections and settings from the chosen file

Profiles are useful for switching quickly between preset configurations (e.g. a two-player setup vs. a solo setup).

---

### Reference Tabs

Four read-only reference tabs let you look up limited information without leaving the app. This is a work in progress, more details will be available in future releases:

| Tab                    | Contents                                                                        |
| ---------------------- | ------------------------------------------------------------------------------- |
| **Spirits (Info)**     | All spirits and aspects; sortable by name, complexity, or expansion; searchable |
| **Boards (Info)**      | All boards; terrain by land number, setup components by land number             |
| **Adversaries (Info)** | All adversaries; difficulty level by Adversary level                            |
| **Scenarios (Info)**   | All scenarios; no additional information is provided in this section            |

---

## Checkbox States

All entity lists (spirits, aspects, boards, adversaries, scenarios) use tristate checkboxes:

| State         | Appearance      | Meaning       | Effect on game setups                                 |
| ------------- | --------------- | ------------- | ----------------------------------------------------- |
| **Unchecked** | ☐ Empty         | Never select  | Item will never appear in a generated game setup      |
| **Checked**   | ☑ Filled        | Optional      | Item may or may not appear — chosen at random         |
| **Forced**    | ◼ Red highlight | Always select | Item **always** appears in every generated game setup |

- **Left-click** cycles forward: Unchecked → Checked → Forced → Unchecked
- **Right-click** cycles backward: Unchecked → Forced → Checked → Unchecked

---

## What the App Remembers

The app automatically saves and restores the following items between sessions:

- Window size and position
- Spirit count slider value
- All checkbox states (spirits, aspects, boards, adversaries, scenarios)
- All control panel settings (expansion toggles, board options, play options)
- Tree expansion state (which spirits are expanded in the spirit list)

No manual save is needed — state is written automatically when the app closes.

---

## Troubleshooting

### The app won't start

- Make sure you extracted all zip parts before running
- Ensure you run `SIRPYv4.exe` from inside the extracted `SIRPYv4` folder, not directly from the zip

### Windows shows a security warning

- Click **More info** then **Run anyway** — the app is unsigned but safe
- If your organisation blocks unsigned executables, run from a personal machine
- On Windows 11, if you are using Smart App Control you will not be able to run SIRPY for Windows because the code is unsigned. It's unlikely that this will ever change

### Launch button does nothing

- For web launch, check your internet connection and default browser
- For Steam launch, verify Spirit Island Digital is installed and Steam is running and that Spirit Island is *not* running (this is a Handelabra Launch requirement)

### Selections or settings were lost

- State files live in `%APPDATA%\SIRPYv4\`. If they become corrupted, delete them and the app will start fresh
- Use **Save Setup** regularly to preserve configurations you care about

### App log

- Diagnostic logs are written to `%APPDATA%\SIRPYv4\app.log` (auto-rotated, capped at ~30 KB)

---

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for the full version history.

---

## License

This project is licensed under the [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International](https://creativecommons.org/licenses/by-nc-nd/4.0/) license (CC BY-NC-ND 4.0).

You may share this software freely with attribution. You may not use it for commercial purposes or distribute modified versions.
