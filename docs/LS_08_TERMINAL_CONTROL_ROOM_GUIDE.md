# LS-08 Terminal Area and Control Room Blockout Guide

This guide supports LS-08: Build Terminal Area and Control Room blockout.

The actual room changes should be made in Unreal Editor inside:

```text
Content/Maps/LVL_Level01_LastShift.umap
```

Do not hand-edit `.umap` files outside Unreal.

## Goal

Build the final progression spaces for Level 1. The player should be able to follow the Main Corridor to the Terminal Area, identify the Control Room as the destination, and understand where the final terminal will be placed later.

## Scope For LS-08

Build only the Terminal Area and Control Room blockout. Do not implement terminal Blueprint logic, door unlock logic, lockdown ending, final lighting, final audio, UI, or Marketplace dressing yet.

## Required Outputs

- Terminal Area connected from Main Corridor
- Placeholder terminal desk or wall console in Terminal Area
- Locked-looking Control Room route or door placeholder
- Control Room space that feels like a destination
- Final terminal location inside Control Room
- Placeholder control panels or equipment silhouettes
- Clear player path from corridor to Terminal Area
- Collision-clean floors, walls, and openings

## Layout Intent

The Terminal Area should be the last readable step before the Control Room.

Recommended relationship:

```text
[MAIN CORRIDOR] -> [TERMINAL AREA] -> [CONTROL ROOM]
```

The player should understand:

1. The Terminal Area is important.
2. The Control Room is the final destination.
3. The Control Room access is special, blocked, or locked-looking until later gameplay systems exist.

## Suggested Scale

Use the same blockout unit scale as the current map. These are practical targets, not strict measurements.

| Element | Suggested Size |
| --- | --- |
| Terminal Area | Medium room or widened corridor area |
| Control Room | Medium destination room, similar or slightly smaller than Start Office |
| Door / opening width | About 2 to 3 blockout units |
| Terminal placeholder | About 2 x 1 x 2 or 3 x 1 x 2 blockout units |
| Wall console placeholder | About 3 x 1 x 2 blockout units |
| Control panel row | About 4 to 8 units wide along a wall |
| Walkable clearance | At least 2 units on required paths |

Prioritize readability. The player should instantly notice the Terminal Area and understand that the Control Room is the target.

## Step-By-Step Unreal Editor Tasks

1. Open `LastShift.uproject`.
2. Open `Content/Maps/LVL_Level01_LastShift`.
3. Save immediately before editing.
4. Locate the Terminal Area from the LS-04/LS-06 corridor route.
5. Shape the Terminal Area so it is visible from or clearly connected to the Main Corridor.
6. Add a placeholder terminal desk, wall console, or workstation.
7. Add a clear Control Room door or doorway placeholder.
8. Make the Control Room access look important or locked, using only blockout shapes.
9. Shape the Control Room as a destination space, not another random side room.
10. Add the final terminal placeholder inside the Control Room.
11. Add simple control panel or equipment silhouettes along one wall.
12. Keep the player path clear from Terminal Area to Control Room entrance.
13. Remove any geometry that makes the final route confusing.
14. Save the level.

## Terminal Area Requirements

The Terminal Area should communicate:

- This is a systems access area.
- A terminal will matter here later.
- The Control Room route depends on this space.

Use placeholder geometry for:

- Terminal desk or wall console
- Monitor block
- Locked door indicator location
- Short log/message location
- Small floor area where the player can stand and face the terminal

## Control Room Requirements

The Control Room should communicate:

- This is the Level 1 destination.
- The final terminal will trigger the ending later.
- The space has facility control equipment.

Use placeholder geometry for:

- Final terminal
- Control panel row
- Chair or console station
- Observation window or blocked observation wall if it fits the current layout
- Lockdown light placeholder locations, but not final lighting yet

## Player Guidance

Use simple blockout guidance:

- Terminal visible from the corridor route or framed by the room entrance
- Control Room door/entry visible from Terminal Area
- Final terminal placed as a focal point inside Control Room
- Fewer props in the required walking path
- Strong room silhouette so Control Room feels like an endpoint

## What Not To Add Yet

- No working terminal interaction
- No UI terminal messages
- No door unlock Blueprint
- No lockdown trigger
- No alarm lights or sirens
- No final post-process or lighting pass
- No entity reveal or scare setup
- No detailed Marketplace dressing

## Smoke Test Checklist

After editing, press Play in Editor and verify:

- Player can reach Terminal Area from Main Corridor.
- Terminal Area is easy to identify.
- Placeholder terminal is visible and reachable.
- Control Room route or locked placeholder is easy to locate.
- Control Room feels like a destination, not a random extra room.
- Final terminal placeholder has a clear placement.
- Player can walk around the Terminal Area without getting stuck.
- Player can enter or approach the Control Room area as intended for the current blockout.
- Collision works on walls, floors, and doorway edges.
- The final route does not confuse the main path.
- No gameplay logic is required to complete this pass.

## Expected Files To Commit

Unreal may update or create files such as:

```text
Content/Maps/LVL_Level01_LastShift.umap
Content/__ExternalActors__/Maps/LVL_Level01_LastShift/...
Content/__ExternalObjects__/Maps/LVL_Level01_LastShift/...
```

This guide may also be committed:

```text
docs/LS_08_TERMINAL_CONTROL_ROOM_GUIDE.md
```

Do not commit generated folders:

```text
Saved/
Intermediate/
DerivedDataCache/
```

## Done Means

LS-08 is done when:

- Terminal Area exists and is connected from the Main Corridor.
- Placeholder terminal is easy to find.
- Control Room route or locked placeholder is clear.
- Control Room feels like the final destination.
- Final terminal placeholder is clearly placed.
- The level still runs in Play in Editor.
