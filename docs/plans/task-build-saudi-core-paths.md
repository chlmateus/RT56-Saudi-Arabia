# Task: Build Saudi Arabia's Core Focus Paths (5 Branches)

**Recommended mode:** 🌳 Focus Architect
**Files involved:** the Saudi Arabia focus tree file in `common/national_focus/`
(the same file already containing `SAU_guardians_of_the_holy_sites` and
`SAU_arab_unity_vision`)

## Context
The tree already has three paths built: Abbasid Restoration, Guardians of the
Holy Sites, and Arab Unity Vision. Build these five additional paths as new
branches in the same file, without touching the three existing ones.

## Overall structure
1. **Trunk: House of Saud Consolidation** — 3 to 4 focuses long. This is the
   tree's base branch; it should end in a single "crossroads" focus where the
   ideology paths below fork off.
2. **Ikhwan Resurgence** — branches off early from the trunk (around the 2nd
   trunk focus), 3 to 5 focuses deep. Historically the Ikhwan rebelled against
   the Saudi state once it consolidated, so this can be `mutually_exclusive`
   with continuing further down the trunk/ideology paths, or an alternate
   early fork — your call which reads better once you see the trunk focuses.
3. **Three ideology paths, forking from the trunk's crossroads focus, all
   `mutually_exclusive` with each other:**
   - Wahhabi Fundamentalism (fascism-equivalent), 10 to 20 focuses deep
   - Arab Socialist Uprising (communism-equivalent), 10 to 20 focuses deep
   - Constitutional Reform (democracy-equivalent), 10 to 20 focuses deep

**Size guidance:** each ideology path is a full arc, 10 to 20 focuses —
enough room for sub-branches, internal forks, and a real escalation from
early moves to late-game payoffs, not just a straight single-file line of
focuses. Feel free to let a path split into 2 short internal sub-branches
that later reconverge, rather than forcing 10-20 focuses into one single
chain. Ikhwan stays 3 to 5 focuses, the trunk stays 3 to 4 — only the three
ideology paths are getting bigger. Don't pad with meaningless filler focuses
just to hit the count; every focus should do something.

## Positioning rules
- Keep the whole thing visually compact — small x/y steps between connected
  focuses (steps of 1-2, similar to the generic shared focus file's spacing),
  not spread out across a huge area of the grid.
- **Every focus below a path's root must chain to the focus directly above it
  in that same path using `relative_position_id`** — not back to the trunk
  every time, just to its immediate parent. This means moving any single
  focus shifts everything below it, and moving the trunk's root focus
  cascades through the entire tree.
- Each ideology path's first focus should use `relative_position_id` pointing
  to the crossroads focus, then every focus after that within the same path
  points to the one directly before it.
- Double-check no focus in the new branches overlaps an existing focus's
  effective x/y position once relative offsets are accounted for.

## Content rules (from project rules — repeated here for this task)
- Reuse existing RT56 scripted effects/triggers/modifiers where they fit; do
  not invent new effect or trigger names.
- Every new focus needs realistic `cost`, `prerequisite`, `mutually_exclusive`
  (where relevant), and a `completion_reward` that isn't empty/placeholder.
- Every new focus needs a matching localisation key:
  ```
  l_english:
   focus_SAU_example_key:0 "Display text here"
   focus_SAU_example_key_desc:0 "Longer description text here"
  ```

## Before reporting done
- List every focus created, grouped by which of the 5 paths it belongs to.
- Confirm the `relative_position_id` chain for each path (state which focus
  points to which).
- Confirm bracket balance and UTF-8 no-BOM.
- Flag anything you weren't fully sure existed (an effect, modifier, or icon)
  instead of presenting it as confirmed working.
