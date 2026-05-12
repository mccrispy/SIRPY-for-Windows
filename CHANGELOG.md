# Changelog — Spirit Island Randomizer

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [4.4.0] - 2026-05-12

### Changed

- **Spirit selection filters replaced with dropdown panels**: The expansion filter row (six individual checkboxes) has been replaced with three filter dropdowns — Expansion, Complexity, and Name — each opening a floating popup panel. Each filter can be toggled on/off independently without losing its configured values, and has its own Clear button. The old "Clear Filters" button is now "Clear All Filters" and resets all three at once. Active filters are highlighted in blue; filters that have saved selections but are temporarily disabled show a lighter accent. Filters combine with AND logic (a spirit must pass all active filters to appear).

### Added

- **Forced-aspect badge on collapsed spirit rows**: When one or more aspects under a base spirit are set to forced inclusion (☒), a small red `☒ N` badge now appears on the base spirit's row. The badge remains visible even when the tree is collapsed, so forced aspect selections can no longer be accidentally hidden from view.
- **Forced spirit names highlighted in results**: When a spirit was forced (mandatory inclusion, shown with the ☒ checkbox), its name now appears in red in the results panel, matching the colour used in the selection panel.
- **Complexity and expansion labels in the spirit reference list**: Each spirit in the Reference → Spirits list now shows its complexity rating and expansion abbreviation after its name (e.g. `Lightning's Swift Strike (Low) [BG]`). When sorted by Complexity, list rows are colour-coded by complexity tier (green/yellow/orange/pink); when sorted by Name or Expansion, rows are colour-coded by expansion.

### Fixed

- **Aspect names no longer appear with a yellow highlight on light OS themes**: Aspect names in the results panel were rendered with a dark olive background colour that looked like a dirty yellow smudge on light system themes. The background has been removed; aspect names are now displayed in bold italic, which is visually distinct and theme-neutral. The italic style is also applied consistently in the spirit selection tree.
- **No white flash on startup**: The main window no longer briefly appears as a blank white frame before the UI is fully rendered. The window is now hidden during construction and only becomes visible once all layout and paint passes are complete.

## [4.4.0-rc.4] - 2026-05-05

### Changed

- **Thematic board layout diagram**: When Thematic Boards is active, the layout panel now shows the thematic board arrangement diagram for the current player count (e.g. the fixed clockwise compass layout for 4 players) instead of a blank ocean background. The diagram updates immediately when the player count changes, just like the standard layout diagrams.

### Fixed

- **Thematic Boards toggle now updates the layout display immediately**: Checking "Thematic Boards" now replaces the board layout diagram with the plain ocean background at once, rather than continuing to show the standard layout SVG. Unchecking restores the diagram for whichever layout was selected before thematic mode was enabled.
- **Thematic Boards toggle with an existing result now converts the board assignments**: When a result is already showing, enabling Thematic Boards reassigns the selected spirits to the fixed thematic board set for the current player count (sequentially, in thematic compass order). The spirits themselves are unchanged. Disabling Thematic Boards restores the original board assignments exactly as they were before the toggle. If the result has 6 spirits plus an additional board (7 total), the additional board is automatically dropped when switching to thematic mode and restored when switching back; a status bar message explains this. Results with more than 6 spirit boards (not reachable via the UI) cause the checkbox to revert with an error.
- **Layout selection preserved across thematic toggle**: Enabling and then disabling Thematic Boards now restores the layout the user had chosen before enabling thematic mode (e.g. "Coastline"), instead of defaulting back to Standard.

## [4.4.0-rc.3] - 2026-05-05

### Added

- **Preferred layout per board count**: A "Preferred" checkbox next to the Board Layout selector lets you mark the current combo selection (any option, including Random) as the default for the current total board count. The app remembers the preference across sessions and automatically applies it whenever the board count changes to that value.
- **Use Adversaries / Use Scenarios toggles**: Two new checkboxes in the Play Options section of the Options panel let you enable or disable adversary and scenario inclusion independently when generating a result. Unchecking either toggle causes generation to produce a result with no adversary or no scenario respectively, without touching any of the individual adversary/scenario tristate selections. Both settings are persisted across sessions and saved/restored with profiles.
- **Board layout diagram**: The results panel now shows a diagram of the selected board layout. For any named layout (including Standard), the diagram appears as soon as you change the Layout dropdown — no need to generate first. For "Random", the diagram appears once a result is generated and reflects the layout that was actually resolved. The diagram scales with the window while preserving its aspect ratio, on a pale blue ocean background. Archipelago shows a "Player-defined" label instead of a diagram, since Archipelago arrangements are set up by the players after launching the game.
- **Layout diagram border**: The board layout diagram now has a 12 px ocean background border on all sides, giving it a framed appearance.

### Fixed

- **Other Pools panels restore to correct width after visiting an info tab**: Switching to any "(Info)" tab expanded the left pane to full window width. On returning to "Other Pools", a leftover column-stretch from grid mode was not cleared, leaving the board, adversary, and scenario panels squished to roughly a quarter of their correct width.
- **Layout name now shown in results for Standard layout**: The "Layout:" line was previously suppressed when Standard was selected. It now always appears in the results.
- **Additional board always shown in results**: When Standard layout was active, the additional board was not listed in the results text. It is now always shown regardless of layout.

### Changed

- **Spirit/board sequence in the launch URL matches the displayed listing order**: Previously, board positions in the URL were assigned by a separate shuffle, so position 1 in the URL could belong to any spirit in the listing. The URL sequence now directly mirrors the spirit/board listing — pair 1 in the results is position 1 in the URL, pair 2 is position 2, and so on. The additional board, if any, continues to appear last in the `boards=` parameter.
- **Board Positions listing removed from results**: The numbered "Position N: Board X" lines have been removed. Position is now implicit from the listing order of the spirit/board pairs, and the layout name and additional board are shown directly below the pairs instead.
- **Generate button and spirit count slider moved to results pane**: The Generate button and Num Spirits slider now sit directly above the results panel instead of in a separate top bar. This places them closer to where results appear and closer to the Options panel where configuration happens, making the generate-then-read flow more natural.
- **Options panel section order**: The Options panel now presents sections in the order a user would typically think about them — Expansions first (which determines what content is available), then Play Options (how to play), then Board Options (how the table is set up). Previously Board Options appeared first.
- **"Include Adversary" and "Include Scenario" checkboxes**: The Play Options checkboxes previously labelled "Use Adversaries" and "Use Scenarios" have been renamed to "Include Adversary" and "Include Scenario" to better distinguish them from the individual adversary/scenario pool selections in the Other Pools tab.
- **Tab names clarified**: The six tabs have been renamed to make their purpose immediately clear. "Spirit Selection" → "Spirit Pool"; "Board/Adv/Scen Selection" → "Other Pools"; "Spirits Reference" → "Spirits (Info)"; "Boards Reference" → "Boards (Info)"; "Adversaries Reference" → "Adversaries (Info)"; "Scenarios Reference" → "Scenarios (Info)". The "(Info)" suffix distinguishes read-only reference tabs from the interactive pool-selection tabs.
- **"Save Setup" / "Load Setup" buttons**: The profile save and load buttons have been renamed from "Save Profile" / "Load Profile" to "Save Setup" / "Load Setup" to better distinguish saved configuration files from saved game results ("Save Result" / "Load Result").

## [4.4.0-rc.2] - 2026-04-22

### Added

- **Board Layout selector**: A new "Board Layout:" dropdown in the Board Options panel lets you choose how boards are physically arranged. Fifteen named layouts are available (e.g. Coastline, Leaf, Star, Archipelago) alongside "Random", which picks a valid layout automatically. The selected layout is shown in the results panel ("Layout: X", "Position 1: Board A", …) and encoded in the Spirit Island app launch URL so the layout is pre-loaded for you.

### Changed

- **Results panel layout reorganised**: The layout name and board position listing now appear below the spirit/board assignments, immediately before the adversary and scenario section. A vertical gap separates the board setup from the game modifiers. The additional board (if any) is always marked inline within the position listing (e.g. "Position 2: E (Additional)") rather than as a separate line.
- **Standard layout now shows Board Positions**: Selecting the Standard layout now assigns boards to numbered positions and displays the Board Positions block in the results panel, matching the behaviour of named layouts. No facing-pair URL parameter is emitted (Standard has no geometry), and the "Layout:" label is suppressed since it adds no information.
- **Strict Board Compatibility restores on board count reduction**: When the board count is reduced back to 4 or fewer after being at 5+, the Strict Board Compatibility checkbox now returns to whatever state the user had set before the count exceeded 4, rather than staying cleared.
- **Removed the user control for UseTokens**: The "Use Tokens" checkbox has been removed. The app now sets the `useTokens` game option automatically whenever Branch & Claw or Jagged Earth is selected — no manual toggle required.

### Internal

- **Robust layouts.json loading**: `layouts.json` is now validated against a dedicated JSON Schema (`layouts_v4.json`) derived from a new LinkML YAML source (`layouts_v4.yaml`). Invalid or malformed files degrade gracefully (layouts combo is hidden; the rest of the app is unaffected). Duplicate canonical names are detected and skipped with a log warning.

## [4.3.0] - 2026-04-17

### Added

  No user features were added in this version.

### Changed

- **Save/Load dialogs now open in Documents\SIRPYv4\\**: File dialogs for Results and Profiles
  now default to the user's Documents folder, which is a more natural location for files
  you intentionally save and share.

- **Board compatibility warnings**: The app now shows a warning when Strict Board Compatibility is disabled and the resulting board
  combination is known to produce very swingy games.

### Fixed

- **Expansion data corrections**: Various corrections to spirit, board, and adversary data
  across multiple expansions.

## [4.2.0] - 2026-04-14

### Added

- **Force any item into every combo**: The forced (red) tristate state — previously only
  available for Spirits and Aspects — now works for Boards, Adversaries, and Scenarios too.
  Set any item to red to guarantee it appears in every generated result.

- **Right-click to reverse-cycle tristate checkboxes**: Right-clicking a checkbox cycles
  the state in reverse order, making it faster to reach a particular state.

### Fixed

- **Aspect selection bug**: Fixed a bug where selecting an Aspect could produce an incorrect
  result in certain edge cases due to a name-matching error in the lookup logic.

## [4.1.0] - 2026-04-08

### Added

- **Launch in Spirit Island Digital**: A new Launch button generates a URL for your current
  combo and opens it directly in Spirit Island Digital — via the Handelabra launch page or directly local. The Handelabra launch page works for both Steam and non-Steam Spirit Island Digital, which is moot for this Windows only app.

- **Window position and spirit count are now remembered**: The app restores its size,
  position, and the spirit count slider to where you left them on your last session.

- **Forced items highlighted in red**: Items locked into every combo are now shown with a
  red background and bold text, making them easy to spot at a glance.

## [4.0.0] - 2026-04-05

### Added

- **Tree view for Spirit Selection**: Spirits and their Aspects are now displayed in a
  collapsible tree, making it easy to see which aspects belong to which spirit.

- **Quick selection modes**: New "Base Only" and "Aspects Only" buttons let you switch
  your spirit selection instantly without manually checking each item.

- **Strict Board Compatibility toggle**: A checkbox in the control panel lets you choose
  whether board placement constraints are enforced when generating combinations.

### Fixed

- **4 spirits + additional board always failed**: Selecting 4 spirits with "Include
  Additional Board" enabled previously produced no valid result every time. This is now
  fixed and works correctly.
