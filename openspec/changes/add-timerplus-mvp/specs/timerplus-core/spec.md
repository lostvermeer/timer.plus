# TimerPlus Core Spec

## ADDED Requirements

### Requirement: Create Timer Routine
Users SHALL be able to create a timer routine with a name, work duration, rest duration, and number of rounds.

#### Scenario: User creates a valid routine
- WHEN the user enters a routine name, work duration, rest duration, and number of rounds
- AND saves the routine
- THEN the routine SHALL be saved locally
- AND the routine SHALL appear in the presets list

### Requirement: Validate Timer Routine
The app SHALL prevent users from saving invalid timer routines.

#### Scenario: User enters invalid values
- WHEN the user tries to save a routine with missing or invalid values
- THEN the app SHALL show a validation message
- AND the routine SHALL NOT be saved

### Requirement: Run Timer Routine
Users SHALL be able to start a timer routine.

#### Scenario: User starts a routine
- WHEN the user starts a routine
- THEN the app SHALL show the active phase
- AND the app SHALL show the remaining time
- AND the app SHALL show the current round

### Requirement: Pause And Resume Timer
Users SHALL be able to pause and resume an active timer.

#### Scenario: User pauses the timer
- WHEN the user pauses the timer
- THEN the countdown SHALL stop
- AND the current remaining time SHALL stay visible

#### Scenario: User resumes the timer
- WHEN the user resumes the timer
- THEN the countdown SHALL continue from the paused time

### Requirement: Reset Timer
Users SHALL be able to reset an active timer.

#### Scenario: User resets the timer
- WHEN the user resets the timer
- THEN the timer SHALL return to the beginning of the routine
- AND the timer SHALL stop running

### Requirement: Complete Routine
The app SHALL clearly show when a routine is complete.

#### Scenario: Routine reaches the final round
- WHEN the final work/rest phase finishes
- THEN the app SHALL stop the timer
- AND the app SHALL show a completion state