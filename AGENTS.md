# Training Log project guidance

## Project

- This is a single-page workout tracker for desktop browsers and mobile Web Clips, with particular emphasis on iPhone 15 Pro.
- The app lives in `index.html`, including its HTML, CSS, and vanilla JavaScript. Keep the app simple; introduce dependencies or a build system only when the requested feature needs them.
- These instructions capture established preferences. Follow newer explicit user requests when they change these preferences.

## Maintaining project continuity

- For every new user instruction concerning this project, review and update this file in the same task to capture any new or changed requirement, preference, or workflow rule.
- Replace superseded guidance rather than accumulating contradictory instructions. The user's latest explicit instruction takes precedence.
- Keep this file concise and organized by topic. Record enduring requirements, not a transcript, routine deployment events, or duplicate entries. If an instruction is already fully captured, no redundant edit is needed.
- Complete the requested work as well as documenting it; updating this file does not replace implementation or verification.
- Briefly mention material guidance updates in the task handoff so the user knows their preferences were retained.

## Layout and visual design

- Prioritize readable, compact cards so several exercises fit on one mobile screen. Reduce unnecessary padding before reducing readable text or usable touch targets.
- Keep Weight (kg), Reps, and Sets visible together in three columns on mobile.
- Keep + directly above − in a close pair on the right of each control. Preserve the goal of easy right-thumb operation.
- Use distinct colors for day tabs and exercise cards, with related shades within each card. Preserve readable text contrast and a clearly marked active tab.
- Keep the heading `Training Log` and the date on one line, using the same font, size, weight, and color. Format dates like `TUE, 15 SEP 2026` using the user's local date.
- Keep exercise names compact: currently 18px on desktop and 16px on mobile.
- Keep tab labels narrow so more days are visible. Long labels must not break the layout, and additional tabs must remain reachable by scrolling.
- Show edit/delete actions only on the active day tab; inactive tabs prioritize the name and switching target.
- Give numeric values visual priority (18px on mobile) and retain 36px-tall mobile +/− buttons alongside the labels and values.
- Store colors on exercises and days so reordering or deleting peers does not change their colors. Use consistent SVG action icons.
- Show the tab-edge fade only while additional content is hidden to the right.
- Do not reintroduce the large `Today's work` heading, the session summary row, or exercise-volume summaries unless requested.

## Interaction requirements

- Clicking a day tab switches days. Only its separate pencil button enters name-editing mode.
- Support adding, renaming, and deleting days. Confirm before deleting a day and its workouts.
- Support adding, renaming, and deleting exercises, with an Undo action after exercise deletion.
- Allow direct numeric entry and quick +/− adjustments. Weights are in kilograms; reps and sets are whole numbers; values must not be negative.
- Keep the refresh button available for Web Clips.
- Support exercise reordering with a visible drag handle on desktop and touch devices, and persist the order within the correct day.
- During dragging, show an insertion line and scroll near viewport edges. Support upward/downward placement, including after the last card, Escape/cancel, and arrow-key reordering from the handle.
- Update numeric fields and edited names in place, preserving focused inputs and buttons instead of rebuilding cards and tabs for each adjustment.
- Use semantic controls, descriptive accessible labels, visible keyboard focus, and accessible feedback. Avoid shrinking touch targets merely to achieve density.

## Saved data and defaults

- User workouts are stored in localStorage under `rep-sessions`; `rep-workouts` is the legacy key supported during migration.
- Preserve existing sessions, names, numbers, and exercise order when changing the interface or defaults. Never clear storage as part of a normal update or verification.
- Defaults apply only to new users. Default tabs are `Day 1`, `Day 2`, and `Day 3`.
- Day 1 defaults, in order: `Romanian Deadlift`, `Bulgarian Split Squats`, `Nordic Hamstring Curls`, and `Leg Press`. Each starts at 0 kg, 10 reps, and 3 sets. Days 2 and 3 start empty.
- Use Title Case for default names, but preserve user-entered names as entered.
- Escape user-entered text when inserting it into HTML.
- Saved feedback must reflect successful storage. GitHub publishing does not synchronize users' workout data between devices.

## Verification

- Match verification to the change. Check JavaScript syntax for script edits and inspect responsive layout for layout changes when browser access is available.
- Use a 393px-wide portrait viewport as the main iPhone 15 Pro layout check, plus a narrow 320px viewport and a desktop width. Check clipping, horizontal overflow, and control reachability.
- For relevant interaction changes, verify day switching versus renaming, numeric changes, refresh persistence, deletion cancellation, Undo, and reorder persistence.
- Test reordering both upward and downward, including adjacent cards and moving a card to the end. A syntax check alone does not establish drag-and-drop behavior.
- Use isolated test data when testing mutations. Do not alter or delete real saved workouts during verification.
- If visual or interaction testing is blocked, state that limitation; do not claim the page was visually verified or that interactions were tested.

## GitHub publishing

- The established public repository is `neeyh/workout-tracker2`, with `index.html` on `main`.
- For a deploy or sync request, inspect the current remote file before uploading. Preserve unrelated remote edits and check the current file SHA when using the GitHub contents API.
- Verify the resulting remote revision after publishing.
- Distinguish a successful source upload from a live website deployment. Claim that the live site updated only after verifying the hosting result.
- Keep user changes intact, and avoid unrelated refactors during small interface edits.
