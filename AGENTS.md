# Training Log

- Update this file for durable user preferences; replace outdated rules and avoid duplicates.
- Single-file vanilla app: `index.html`; optimize for desktop and iPhone Web Clips (393px/320px).
- Keep cards compact: Weight (kg), Reps, Sets visible together; + above − on the right; readable values and usable touch targets. Keep generous card side gutters for scrolling and place the reorder handle left.
- Header is one line: `Training Log` plus local date `TUE, 15 SEP 2026` in matching typography.
- Keep iOS Web Clip metadata and touch-icon PNG assets current when branding changes.
- Use stable per-day/exercise colors. No large title, session summary, or volume summary unless requested.
- Day tab switches days; pencil alone edits its name; delete confirms. Keep inactive tabs compact.
- Exercises support add, edit, undoable delete, and persistent reorder. Drag handle uses a ghost card, insertion marker, edge scrolling, and keyboard arrows.
- Preserve focus during quick numeric updates; center numeric values. Weights are kg; reps/sets are nonnegative integers.
- Show a clear-name × button while an exercise name field is focused.
- Store sessions in `rep-sessions`; preserve data and support legacy `rep-workouts`. Escape user text.
- New users: `Day 1`–`Day 3`; Day 1 has Romanian Deadlift, Bulgarian Split Squats, Nordic Hamstring Curls, and Leg Press at 0 kg × 10 × 3.
- Verify changed interactions with isolated data; never clear real localStorage. If visual testing is blocked, say so.
- Automatically publish every code change to `neeyh/workout-tracker2` on `main`: fetch remote SHA, preserve unrelated changes, then verify the update.
