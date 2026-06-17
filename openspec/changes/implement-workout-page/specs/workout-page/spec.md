# Workout Page Spec

## ADDED Requirements

### Requirement: Bottom Tab Navigation
The app SHALL provide bottom tab navigation with Workout, Rounds, Stopwatch, and Settings tabs.

#### Scenario: Tab navigation is displayed
- **WHEN** the app navigation shell is rendered
- **THEN** the bottom tab navigation SHALL display Workout, Rounds, Stopwatch, and Settings tabs

#### Scenario: Workout is the default tab
- **WHEN** the user opens the app without selecting another tab
- **THEN** the Workout tab SHALL be active
- **AND** the Workout page SHALL be visible

### Requirement: Placeholder Non-Workout Tabs
The app SHALL expose Rounds, Stopwatch, and Settings as reachable tabs without implementing their functional workflows in this change.

#### Scenario: User opens a placeholder tab
- **WHEN** the user selects the Rounds, Stopwatch, or Settings tab
- **THEN** the selected tab SHALL become active
- **AND** the app SHALL show a minimal placeholder screen for that tab

#### Scenario: Placeholder tabs do not provide feature workflows
- **WHEN** the user views a Rounds, Stopwatch, or Settings placeholder screen
- **THEN** the screen SHALL NOT provide stopwatch controls, rounds configuration, settings controls, or saved routine workflows

### Requirement: Predefined Workout Preset Data
The app SHALL define predefined workout presets as static timer configuration data.

Each workout preset SHALL include:

- Workout name
- Work duration
- Rest duration between rounds
- Number of rounds

A workout preset SHALL preserve the following optional fields when they are defined:

- Number of cycles
- Rest duration between cycles
- Cooldown duration

#### Scenario: Initial presets are available
- **WHEN** the Workout page loads
- **THEN** the predefined workout data SHALL include Tabata, Boxing, and Yoga presets

#### Scenario: Preset contains timer configuration
- **WHEN** a predefined workout preset is rendered
- **THEN** the preset SHALL have a workout name, work duration, rest duration between rounds, and number of rounds
- **AND** the preset SHALL preserve cycle, rest-between-cycles, and cooldown values when those values are defined

### Requirement: Workout Preset List
The Workout page SHALL display the predefined workout presets in a mobile-friendly list layout.

#### Scenario: User views workout presets
- **WHEN** the user views the Workout page
- **THEN** the page SHALL display a list of predefined workout presets
- **AND** each listed workout SHALL show its name and timer summary

#### Scenario: Workout list fits mobile layout
- **WHEN** the Workout page is viewed on a mobile-sized screen
- **THEN** the workout list SHALL remain readable without horizontal scrolling
- **AND** the list content SHALL not be hidden behind the bottom tab navigation

### Requirement: Read-Only Workout Items
Workout preset items SHALL be read-only in this change.

#### Scenario: Workout item has no start action
- **WHEN** the user views a workout preset item
- **THEN** the item SHALL NOT provide a start timer action
- **AND** the app SHALL NOT start a countdown from the Workout page

#### Scenario: Workout item has no editing or saving actions
- **WHEN** the user views a workout preset item
- **THEN** the item SHALL NOT provide edit, create, delete, or save controls
- **AND** the app SHALL NOT persist user-created routines from the Workout page
