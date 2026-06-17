# Design: TimerPlus MVP

## Overview
TimerPlus MVP will be a web interval timer app with three main areas: a preset list, a routine editor, and a timer runner.

## Screens
The app will include:

- Presets screen
- Routine editor screen
- Timer runner screen

## Presets Screen
The presets screen shows saved timer routines.

Users can:
- View saved routines
- Start a saved routine
- Edit a saved routine
- Delete a saved routine
- Create a new routine

## Routine Editor Screen
The routine editor lets users configure a timer routine.

Fields:
- Routine name
- Work duration
- Rest duration
- Number of rounds

Validation:
- Routine name is required
- Work duration must be greater than 0
- Rest duration must be 0 or greater
- Number of rounds must be greater than 0

## Timer Runner Screen
The timer runner shows the active routine.

It displays:
- Routine name
- Current phase: work, rest, or complete
- Remaining time
- Current round
- Total rounds

Controls:
- Start
- Pause
- Resume
- Reset

## State Management
The app will manage:

- The list of saved routines
- The routine currently being edited
- The active timer routine
- Whether the timer is idle, running, paused, or complete
- Current phase
- Current round
- Remaining time

## Persistence
Saved routines will be stored locally in the browser using localStorage.

No user account or backend is required for the MVP.

## Timer Accuracy
The timer should calculate remaining time from timestamps instead of only subtracting one second at a time.

This helps keep the timer accurate if the browser slows down or the tab becomes inactive.

## Notifications And Feedback
The app should provide simple feedback when:

- A phase changes from work to rest
- A phase changes from rest to work
- The routine is complete

For MVP, this can be handled with a sound alert or visual change.

## Out Of Scope
The MVP will not include:

- User accounts
- Cloud sync
- Payment features
- Social sharing
- Advanced statistics
- Mobile app store release