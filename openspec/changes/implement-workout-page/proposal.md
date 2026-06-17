# Implement Workout Page

## Why

TimerPlus needs a clear default starting screen where users can quickly choose a workout timer routine.

The Workout page will be the first page users see when they open the app. It should make the app useful immediately by showing predefined workout routines such as Tabata, Boxing, Yoga, and other common timer formats.

This gives users a starting point before they create custom routines.

## What Changes

- Add a bottom tab navigation structure with four main tabs:
  - Workout
  - Rounds
  - Stopwatch
  - Settings

- Make the Workout tab the default page when the app opens.

- Add a Workout page that displays a list of predefined workout routines.

- Each workout item should contain its own timer configuration data, such as:
  - Workout name
  - Work duration
  - Rest duration between rounds
  - Number of rounds
  - Number of cycles, if needed
  - Rest duration between cycles, if needed
  - Cooldown duration, if needed

- Add initial predefined workout items, such as:
  - Tabata
  - Boxing
  - Yoga

- Allow users to view the workout list in a mobile-friendly layout.

## Out Of Scope

This change will not include:

- Running the selected workout timer.
- Editing predefined workouts.
- Creating custom workouts.
- Saving user-created routines.
- Stopwatch functionality.
- Rounds page functionality.
- Settings page functionality.
- Backend storage.
- Cloud sync.

Those features should be handled by separate OpenSpec changes.

## Impact

This change introduces the main app navigation and the first default user-facing page.

It also establishes the initial workout preset data structure that later timer-running and routine-editing features can build on.
