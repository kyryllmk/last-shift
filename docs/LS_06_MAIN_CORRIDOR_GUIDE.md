# LS-06 Main Corridor Blockout Guide

This guide supports LS-06: Build Main Corridor blockout.

The actual corridor changes should be made in Unreal Editor inside:

```text
Content/Maps/LVL_Level01_LastShift.umap
```

Do not hand-edit `.umap` files outside Unreal.

## Goal

Make the Main Corridor function as the navigation spine for Level 1. The player should leave the Start Office and understand the difference between the main route and the side exploration route.

## Scope For LS-06

Build only the Main Corridor blockout. Do not implement door Blueprints, real locks, final lighting, audio triggers, Marketplace props, or detailed environmental art yet.

## Required Outputs

- Clear corridor route from Start Office
- Connection to Storage Room / side route
- Connection toward Terminal Area
- Placeholder control route or locked-control-door location
- Placeholder signage for main route, storage, terminal, and control
- Collision-clean walls and floor
- No confusing dead ends

## Current Layout Intent

Use the existing LS-04 map layout. Do not rebuild the whole level.

The corridor should support this route:

```text
[START OFFICE] -> [MAIN CORRIDOR] -> [TERMINAL AREA] -> [CONTROL ROOM]
                       |
                  [STORAGE ROOM]
                       |
                  [FUSE ROOM]
```

## Suggested Scale

Use the same blockout unit scale as the current map. These are practical targets, not strict measurements.

| Element | Suggested Size |
| --- | --- |
| Corridor width | About 4 to 6 blockout units |
| Door / opening width | About 2 to 3 blockout units |
| Hall wall height | Match existing wall height |
| Side branch width | About 3 to 5 blockout units |
| Sign placeholder | About 2 x 1 blockout units on wall |
| Warning/control placeholder | About 2 x 2 blockout units near control route |

Prioritize navigation over exact numbers. The player should move comfortably without the hallway feeling like an empty warehouse.

## Step-By-Step Unreal Editor Tasks

1. Open `LastShift.uproject`.
2. Open `Content/Maps/LVL_Level01_LastShift`.
3. Save immediately before editing.
4. Locate the current Main Corridor area from the LS-04 blockout.
5. Confirm the Start Office exit leads into the corridor cleanly.
6. Shape the corridor so it has a clear forward path toward the Terminal Area.
7. Add or confirm the side opening toward Storage Room.
8. Add or confirm a control route / control door placeholder.
9. Add simple wall or floor placeholders that make the corridor boundaries readable.
10. Add placeholder signage blocks or text labels for:
    - `STORAGE`
    - `TERMINAL`
    - `CONTROL`
    - optional `AUTHORIZED PERSONNEL`
11. Add one blocked-looking or locked-looking control placeholder if the route is not meant to open yet.
12. Remove or simplify any geometry that creates accidental dead ends.
13. Save the level.

## Corridor Readability Rules

The corridor should do three jobs:

- Show the player where the main path continues.
- Make the side route discoverable without making it look like the main ending route.
- Hint that the Control Room is important but not fully accessible yet.

Use simple blockout tools:

- Wider opening for main path
- Smaller or side-facing opening for storage route
- Wall sign placeholders
- A blocked or locked-looking control doorway
- Clear empty floor space where the player must walk

## Placeholder Signage Ideas

Use simple planes, cubes, or Text Render actors. Keep them temporary.

Good labels for this pass:

```text
STORAGE
TERMINAL ACCESS
CONTROL ROOM
POWER / MAINTENANCE
RESTRICTED
```

These do not need final fonts, materials, or UI styling yet.

## What Not To Add Yet

- No working doors
- No keycards
- No fuse gameplay
- No terminal interaction
- No final horror lighting
- No sound triggers
- No detailed Marketplace dressing
- No monster hints yet unless they are simple placeholder marks

## Smoke Test Checklist

After editing, press Play in Editor and verify:

- Player exits Start Office into Main Corridor smoothly.
- Corridor forward direction is easy to understand.
- Storage / side route is visible but does not confuse the main path.
- Terminal Area direction is readable from the corridor.
- Control Room route or placeholder is identifiable.
- Player does not get stuck on corners, signs, or wall edges.
- Corridor walls block the player correctly.
- There are no accidental holes or collision gaps.
- There are no confusing dead ends created by LS-06 changes.
- Placeholder signs help orientation without needing final art.

## Expected Files To Commit

Unreal may update or create files such as:

```text
Content/Maps/LVL_Level01_LastShift.umap
Content/__ExternalActors__/Maps/LVL_Level01_LastShift/...
Content/__ExternalObjects__/Maps/LVL_Level01_LastShift/...
```

This guide may also be committed:

```text
docs/LS_06_MAIN_CORRIDOR_GUIDE.md
```

Do not commit generated folders:

```text
Saved/
Intermediate/
DerivedDataCache/
```

## Done Means

LS-06 is done when:

- The Main Corridor connects Start Office, side route, Terminal Area direction, and Control Room placeholder.
- The player can identify main and side paths.
- Placeholder signage exists.
- Collision is clean.
- The level still runs in Play in Editor.
