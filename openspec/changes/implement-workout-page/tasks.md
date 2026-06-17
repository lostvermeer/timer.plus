# Tasks: Implement Workout Page

## 1. App Navigation Shell

- [ ] 1.1 Create the minimal runtime app entry structure needed for the Workout page change
- [ ] 1.2 Add bottom tab navigation with Workout, Rounds, Stopwatch, and Settings tabs
- [ ] 1.3 Configure Workout as the initial/default tab when the app opens
- [ ] 1.4 Ensure the tab shell supports mobile safe areas and leaves space for tab content

## 2. Workout Preset Data

- [ ] 2.1 Define a reusable WorkoutPreset type with required timing fields and optional cycle/cooldown fields
- [ ] 2.2 Add static predefined workout preset data for Tabata, Boxing, and Yoga
- [ ] 2.3 Store preset duration values as numeric timer configuration data
- [ ] 2.4 Add a display helper or mapping for readable workout timing summaries

## 3. Workout Page UI

- [ ] 3.1 Add the Workout page or screen component
- [ ] 3.2 Render the predefined workout preset list on the Workout page
- [ ] 3.3 Show each workout name and timer summary in the list
- [ ] 3.4 Show optional cycle, rest-between-cycles, and cooldown details only when defined
- [ ] 3.5 Make the Workout list mobile-friendly without horizontal scrolling or bottom tab overlap

## 4. Placeholder Tabs

- [ ] 4.1 Add a minimal Rounds placeholder screen
- [ ] 4.2 Add a minimal Stopwatch placeholder screen
- [ ] 4.3 Add a minimal Settings placeholder screen
- [ ] 4.4 Ensure placeholder screens do not include functional controls or workflows

## 5. Scope Guards

- [ ] 5.1 Ensure workout preset items are read-only
- [ ] 5.2 Ensure the Workout page does not start a countdown timer
- [ ] 5.3 Ensure the Workout page does not provide edit, create, delete, or save controls
- [ ] 5.4 Ensure this change does not add local persistence, backend storage, or cloud sync

## 6. Verification

- [ ] 6.1 Verify the app opens on the Workout tab by default
- [ ] 6.2 Verify all four bottom tabs are visible and selectable
- [ ] 6.3 Verify Rounds, Stopwatch, and Settings show placeholder screens only
- [ ] 6.4 Verify Tabata, Boxing, and Yoga presets render with timing summaries
- [ ] 6.5 Verify the Workout page remains readable on a mobile-sized screen
- [ ] 6.6 Run the available typecheck, lint, or test commands for the app
