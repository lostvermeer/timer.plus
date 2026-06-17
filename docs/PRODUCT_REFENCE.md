# TimerPlus Product Reference

## Product Summary

TimerPlus is a web interval timer app for people who need structured time-based routines.

The app helps users create, save, and run timer routines made from work periods, rest periods, and repeated rounds. It is designed mostly for workouts but also can be used for focus sessions, stretching, breathing exercises, study blocks, and other repeatable activities.

## Product Goal

The goal of TimerPlus is to make it easy for users to create and run custom interval timers without unnecessary complexity.

A user should be able to open the app, create a routine or choose from the existing workouts, start the timer, pause or reset it when needed, and reuse saved routines later.

## Target Users

### Fitness Users
People who use interval timers for workouts, HIIT, stretching, boxing rounds, circuits, or mobility routines.

### Focus Users
People who use timed work/rest sessions for studying, coding, writing, reading, or deep work.

### Everyday Routine Users
People who need simple repeatable timers for habits, chores, breathing exercises, meditation, or practice sessions.

## Main User Problems

Users need:

- A clear way to create custom timer routines.
- A reliable timer that shows exactly what phase they are in.
- A simple way to pause, resume, and reset.
- A way to save routines so they do not recreate them every time.
- Clear visual and audio feedback when a phase changes.
- A clean interface that works on desktop and mobile.

## MVP Scope

The MVP should include:

- Creating a timer routine.
- Setting work duration.
- Setting number of rounds.
- Setting rest duration beetween rounds.
- Setting cooldown when workout is finished.
- Naming a routine.
- Starting a routine.
- Pausing and resuming a routine.
- Resetting a routine.
- Showing the current phase.
- Showing remaining time.
- Showing current round and total rounds.
- Saving routines locally.
- Loading saved routines.
- Editing saved routines.
- Deleting saved routines.
- Basic visual feedback when phases change.
- Basic sound alert or placeholder for sound alert.

## Out Of Scope For MVP

The MVP will not include:

- User accounts.
- Cloud sync.
- Payments.
- Subscriptions.
- Social sharing.
- Public routine library.
- Advanced statistics.
- Calendar integration.
- Wearable device integration.
- Native mobile app release. <!--do not need a realease to the app store, but I need the mobile version of the app now not the web version and only the ios now ,no android now-->
- Team or coach management.
- AI routine generation.

These can be added later as separate OpenSpec changes.

## Core Concepts

### Routine
A routine is a saved timer configuration.

A routine contains:

- Name
- Work duration
- Rest duration
- Number of rounds <!-- we need here the number of cycles too and the rest beetween the cycles, then the cooldown too -->

Example:

```txt
Name: HIIT Workout
Work: 40 seconds
Rest: 20 seconds
Rounds: 8