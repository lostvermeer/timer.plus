# TimerPlus Product Reference

## Product Summary

TimerPlus is an iOS interval timer app for people who need structured time-based workout routines.

The app helps users create, save, and run timer routines made from work periods, rest between rounds, cycles, rest between cycles, and cooldown periods. It is designed mostly for workouts, but it can also be used for focus sessions, stretching, breathing exercises, study blocks, and other repeatable activities.

The first version should be mobile-first, simple, fast, and usable without an account.

## Product Goal

The goal of TimerPlus is to make it easy for users to create and run custom interval timers on iPhone without unnecessary complexity.

A user should be able to open the app, create a routine or choose from existing workout presets, start the timer, pause or reset it when needed, and reuse saved routines later.

## Target Users

### Fitness Users
People who use interval timers for workouts, HIIT, stretching, boxing rounds, circuits, mobility routines, or gym training.

Fitness users are the primary target users for the MVP.

### Focus Users
People who use timed work/rest sessions for studying, coding, writing, reading, or deep work.

Focus users are supported by the same timer structure, but the MVP should prioritize workout language and workout use cases.

### Everyday Routine Users
People who need simple repeatable timers for habits, chores, breathing exercises, meditation, or practice sessions.

## Main User Problems

Users need:

- A clear way to create custom workout timer routines.
- A reliable timer that shows exactly what phase they are in.
- A simple way to pause, resume, and reset during activity.
- A way to save routines so they do not recreate them every time.
- A way to choose from existing workout presets.
- Clear visual and audio feedback when a phase changes.
- A mobile interface that is easy to read while exercising.
- A simple iOS experience that works without login or internet connection.

## MVP Scope

The MVP should include:

- Native iOS mobile app experience.
- Creating a timer routine.
- Choosing from existing workout presets.
- Naming a routine.
- Setting work duration.
- Setting rest duration between rounds.
- Setting number of rounds per cycle.
- Setting number of cycles.
- Setting rest duration between cycles.
- Setting cooldown duration after the workout is finished.
- Starting a routine.
- Pausing and resuming a routine.
- Resetting a routine.
- Showing the current phase.
- Showing remaining time.
- Showing current round and total rounds.
- Showing current cycle and total cycles.
- Saving routines locally on the device.
- Loading saved routines.
- Editing saved routines.
- Deleting saved routines.
- Basic visual feedback when phases change.
- Basic sound alert or placeholder for sound alert.

## Out Of Scope For MVP

The MVP will not include:

- App Store release.
- Android app.
- Web app.
- User accounts.
- Cloud sync.
- Payments.
- Subscriptions.
- Social sharing.
- Public routine library.
- Advanced statistics.
- Calendar integration.
- Wearable device integration.
- Team or coach management.
- AI routine generation.

These can be added later as separate OpenSpec changes.

## Core Concepts

### Routine
A routine is a timer configuration that can be saved and reused.

A routine contains:

- Name
- Work duration
- Rest duration between rounds
- Number of rounds per cycle
- Number of cycles
- Rest duration between cycles
- Cooldown duration