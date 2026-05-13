# LS-05 Start Office Blockout Guide

This guide supports LS-05: Build Start Office blockout.

The actual Start Office changes should be made in Unreal Editor inside:

```text
Content/Maps/LVL_Level01_LastShift.umap
```

Do not hand-edit `.umap` files outside Unreal.

## Goal

Make the opening room readable, believable, and useful as the first player space. The player should immediately understand that they are in an abandoned office area and that the main route leads out into the facility.

## Scope For LS-05

Build only the Start Office blockout. Do not implement gameplay Blueprints, final lighting, final props, audio, notes UI, or interaction logic yet.

## Required Outputs

- Office walls and playable floor space
- Player start placed inside the office
- One clear exit toward Main Corridor
- Placeholder desk or workstation shapes
- Placeholder location for an evacuation note or first clue
- Simple object silhouettes that sell the room as an office

## Recommended Layout

```text
+------------------------------------------------+
|                                                |
|  [DESK]       [WORKSTATION]       [CLUE SPOT]  |
|                                                |
|                                                |
|  PLAYER START                                  |
|      -> view points toward exit                |
|                                                |
|                                  EXIT TO HALL  |
+-----------------------------------------[]-----+
```

## Suggested Scale

Use the scale of the existing LS-04 blockout. Do not resize the whole map just to match generic Unreal centimeter examples.

Your current Start Office footprint is about `38 x 19` blockout units, which is acceptable for this project. Keep the room compact and make the contents fit that scale.

| Element | Suggested Size |
| --- | --- |
| Room footprint | Keep current footprint, about 38 x 19 blockout units |
| Ceiling height | Match existing wall height |
| Main exit width | Wide enough for the player to pass comfortably, about 2 to 3 blockout units |
| Desk blockout | About 5 x 2 x 2 blockout units |
| Workstation / monitor blockout | About 4 x 2 x 3 blockout units |
| Chair / stool blockout | About 2 x 2 x 2 blockout units |
| Cabinet / shelf blockout | About 2 x 1 x 4 blockout units |
| Walkable space around props | At least 2 blockout units where the player must pass |

If your grid or cube scale differs, prioritize playability: the player should fit through the exit, walk around the desk, and leave the room without snagging on props.

## Step-By-Step Unreal Editor Tasks

1. Open `LastShift.uproject`.
2. Open `Content/Maps/LVL_Level01_LastShift`.
3. Save immediately before editing.
4. Locate the current Start Office area from the LS-04 blockout.
5. Keep the current office footprint unless it feels broken; shape the room only enough to make it readable.
6. Add or adjust walls so the player cannot see the whole level at spawn.
7. Place the player start inside the office.
8. Rotate the player start so the first view points toward the room and hints at the exit.
9. Add simple placeholder cubes for:
   - Desk
   - Workstation or monitor station
   - Chair or stool
   - Filing cabinet, shelf, or storage object
10. Add a small placeholder plane or cube where the first clue will go later.
11. Keep the exit to Main Corridor obvious and unobstructed.
12. Add temporary labels if helpful, such as `START OFFICE`, `EXIT`, and `CLUE`.
13. Save the level.

## Visual Storytelling Targets

Use placeholder shapes only, but arrange them to imply:

- The room was recently occupied.
- The evacuation happened quickly.
- The player is returning to a place that should have people in it.
- The exit into the Main Corridor is the natural next step.

Good placeholder ideas:

- A desk facing away from the exit
- A monitor block on the desk
- One chair slightly offset from the desk
- A notice/clue placeholder near the workstation or door
- A cabinet or shelf along one wall

## Player Guidance

The player should not need text instructions to leave the room.

Use:

- Player start orientation
- Open doorway framing
- Clear floor space
- Slightly brighter placeholder light near the exit if needed
- Fewer props near the exit

## What Not To Add Yet

- No final evacuation note text
- No interactable note Blueprint
- No final office art pass
- No complex clutter
- No audio triggers
- No horror event
- No locked door logic
- No terminal logic

## Smoke Test Checklist

After editing, press Play in Editor and verify:

- Player starts inside the Start Office.
- Player is facing a useful direction, not a blank wall.
- The room reads as an office even with placeholder geometry.
- The exit to Main Corridor is easy to find within a few seconds.
- Player can walk around the desk/workstation without getting stuck.
- Player can leave the room smoothly.
- There are no collision gaps in the office walls.
- The player cannot see confusing unfinished areas from spawn.
- Placeholder clue location is visible but does not block movement.
- The room supports the story setup without adding final narrative systems.

## Expected Files To Commit

Unreal may update or create files such as:

```text
Content/Maps/LVL_Level01_LastShift.umap
Content/__ExternalActors__/Maps/LVL_Level01_LastShift/...
Content/__ExternalObjects__/Maps/LVL_Level01_LastShift/...
```

This guide may also be committed:

```text
docs/LS_05_START_OFFICE_GUIDE.md
```

Do not commit generated folders:

```text
Saved/
Intermediate/
DerivedDataCache/
```

## Done Means

LS-05 is done when:

- The player starts in a readable office.
- The office has clear walls, desks, doorway, and first route.
- Placeholder props support the story setup.
- The exit direction is clear.
- The level still runs in Play in Editor.
