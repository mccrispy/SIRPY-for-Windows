# Changelog — Spirit Island Randomizer

All notable changes to this project are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added

### Changed

### Fixed

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
