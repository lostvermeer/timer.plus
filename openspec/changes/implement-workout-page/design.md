# Design: Implement Workout Page

## Context

TimerPlus needs a default mobile-first starting screen where users can choose from predefined workout timer routines. This change introduces the first app shell by adding bottom tab navigation and making the Workout tab the default entry point.

The current change is intentionally narrower than the full timer product. It establishes navigation and preset data that future timer-running, editing, saving, and settings changes can build on.

The repo currently contains planning artifacts and product documentation, so implementation should introduce the runtime app structure only as needed for this change. The design should not assume existing timer runner, routine editor, storage, or backend code.

## Goals / Non-Goals

**Goals:**

- Add a bottom tab navigation shell with Workout, Rounds, Stopwatch, and Settings tabs.
- Make Workout the initial/default tab.
- Add a mobile-friendly Workout page that lists predefined workout presets.
- Define a typed preset data shape that can later be reused by timer-running and editing features.
- Seed initial presets for Tabata, Boxing, and Yoga.

**Non-Goals:**

- Running a selected workout timer.
- Editing predefined workouts.
- Creating or saving custom workouts.
- Persisting workout data locally or remotely.
- Implementing Stopwatch, Rounds, or Settings functionality.
- Adding backend storage or cloud sync.

## Decisions

### Use Bottom Tabs As The App Shell

Add the four proposed tabs at the top-level navigation layer and make Workout the initial route.

Rationale: bottom tabs match the requested mobile app structure and give later changes stable places to attach Rounds, Stopwatch, and Settings functionality.

Alternatives considered:

- A single Workout screen without tabs: simpler, but it would not establish the requested app navigation.
- Drawer navigation: less appropriate for the primary mobile workflow and not requested.

### Keep Non-Workout Tabs As Minimal Placeholder Routes

Rounds, Stopwatch, and Settings should exist in navigation, but their screens should remain minimal placeholders with no functional workflows.

Rationale: the navigation structure is in scope, but those features are explicitly out of scope. Placeholder routes keep the tab bar complete without creating unfinished behavior.

Alternatives considered:

- Hide inactive tabs until later changes: avoids placeholder screens, but conflicts with the requested four-tab structure.
- Build partial Rounds, Stopwatch, or Settings behavior: creates scope creep and makes this change harder to verify.

### Store Presets In Static Typed Data

Represent the predefined workouts as static app data, separate from the Workout page rendering code.

Use duration values in seconds and optional fields for values that only some routines need:

```ts
type WorkoutPreset = {
  id: string;
  name: string;
  workDurationSeconds: number;
  restBetweenRoundsSeconds: number;
  rounds: number;
  cycles?: number;
  restBetweenCyclesSeconds?: number;
  cooldownSeconds?: number;
};
```

Rationale: numeric duration data is easier for future timer logic to consume than formatted strings. Optional cycle and cooldown fields keep simple routines simple while supporting richer presets.

Alternatives considered:

- Put preset data inline inside the Workout screen: faster initially, but couples display layout to reusable timer configuration data.
- Store presets in local storage immediately: unnecessary because editing and saved user routines are out of scope.

### Make Workout Items Read-Only

Workout items should display routine information but should not start a timer, open an editor, or save anything.

Each item should show the workout name and enough timing summary to distinguish the routine, such as work duration, rest duration, rounds, cycles, and cooldown when present.

Rationale: users can inspect available routines now, and future changes can add item actions without changing the preset data structure.

Alternatives considered:

- Add a Start button per item: this would imply timer-running behavior, which is out of scope.
- Add an edit affordance: editing predefined workouts is also out of scope.

### Use A Mobile-First List Layout

Render the Workout page as a vertically scrollable list that respects safe areas and leaves enough bottom padding for the tab bar.

Preset items should use compact, readable rows or cards with stable spacing and clear hierarchy:

- Workout name as the primary text.
- Timing summary as secondary text.
- Optional cycle/cooldown details only when available.

Rationale: the page should be usable immediately on a phone and easy to scan while preparing for a workout.

Alternatives considered:

- Dense table layout: poor fit for mobile.
- Large marketing-style cards: visually heavier than needed for a functional timer list.

## Risks / Trade-offs

- Placeholder tabs may look unfinished -> Keep their screens intentionally minimal and avoid implying complete functionality.
- Static presets may diverge from future timer runner requirements -> Use a reusable typed data shape with numeric duration fields.
- Users may expect tapping a workout to start it -> Do not add start controls in this change, and keep item behavior read-only.
- Navigation work may be larger if no runtime app shell exists yet -> Keep the app shell minimal and only add structure required by these tabs.

## Migration Plan

1. Add or update the app navigation shell with four bottom tabs.
2. Configure Workout as the initial/default tab.
3. Add the static workout preset type and initial preset data.
4. Add the Workout page list UI.
5. Add minimal placeholder screens for Rounds, Stopwatch, and Settings.
6. Verify the app opens on Workout and the list remains usable on mobile-sized screens.

Rollback is straightforward: remove the new tab shell, Workout page, placeholder tab routes, and preset data introduced by this change.

## Open Questions

- Should the Rounds tab eventually represent saved routines, a custom routine builder, or a separate round-based timer mode?
- Should initial presets stay limited to Tabata, Boxing, and Yoga, or should this change seed additional common workout formats?
