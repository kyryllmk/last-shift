# LS-04 Blockout Implementation Guide

This guide supports LS-04: Create Level 1 blockout map.

The actual `.umap` should be created in Unreal Editor. Do not hand-edit or generate map binary files outside Unreal.

## Target Map

Create this map:

```text
Content/Maps/LVL_Level01_LastShift.umap
```

## Goal

Build a simple playable blockout for Level 1 using basic geometry only. The player should be able to walk the intended route from the Start Office to the Control Room area.

Core route:

```text
[START OFFICE] -> [MAIN CORRIDOR] -> [TERMINAL AREA] -> [CONTROL ROOM]
                       |
                  [STORAGE ROOM]
                       |
                  [FUSE ROOM]
```

## Recommended Unreal Editor Steps

1. Open `LastShift.uproject`.
2. Open the existing template map:

```text
Content/FirstPerson/Maps/FirstPersonMap
```

3. Use `File > Save Current Level As`.
4. Save it as:

```text
Content/Maps/LVL_Level01_LastShift
```

5. Remove template objects that are not needed for the horror blockout, such as weapon pickups, projectile test objects, or decorative template clutter.
6. Keep the First Person player start and basic movement setup.
7. Create the layout with simple cubes, walls, and door openings.
8. Use temporary labels or editor notes for each room.
9. Save the level.

## Suggested Blockout Scale

These dimensions are not strict. They are a starting point for a readable first-person prototype.

| Area | Approximate Size |
| --- | --- |
| Start Office | 900 x 700 unreal units |
| Main Corridor | 1800 x 350 unreal units |
| Storage Room | 700 x 650 unreal units |
| Fuse Room | 600 x 500 unreal units |
| Terminal Area | 800 x 700 unreal units |
| Control Room | 800 x 650 unreal units |
| Door Openings | 120 to 160 unreal units wide |
| Ceiling Height | 300 to 350 unreal units |

## Room Requirements For This Pass

### Start Office

- Player start
- One clear exit to Main Corridor
- Placeholder desk or workstation shapes
- Space for later evacuation note

### Main Corridor

- Clear central route
- Doorway to Storage Room
- Route to Terminal Area
- Blocked or locked-looking route toward Control Room

### Storage Room

- Simple shelves or crate shapes
- Clear route to Fuse Room
- No confusing extra exits

### Fuse Room

- Placeholder fuse location
- Placeholder power panel location
- Small enough to feel like a maintenance room

### Terminal Area

- Placeholder terminal desk or wall console
- Clear view from Main Corridor
- Route toward Control Room door

### Control Room

- Placeholder final terminal
- Space for later lockdown sequence
- Clear end-point feeling

## What Not To Add Yet

- No final art pass
- No combat objects
- No monster
- No puzzle complexity
- No real Blueprint interaction logic
- No audio or lighting polish beyond basic visibility

## Smoke Test Checklist

After saving the map, press Play in Editor and test:

- Player starts inside Start Office.
- Player can walk into Main Corridor.
- Player can find Storage Room.
- Player can reach Fuse Room.
- Player can return to Main Corridor.
- Player can reach Terminal Area.
- Player can reach the Control Room area or its locked placeholder.
- Player cannot easily fall out of the level.
- Collision blocks the player at walls.
- Main route is understandable without signs.
- Side rooms support exploration without feeling like a maze.

## Git Commit Scope

When the map is created, commit only the map-related files Unreal creates for this issue. Expected files may include:

```text
Content/Maps/LVL_Level01_LastShift.umap
Content/Maps/LVL_Level01_LastShift_BuiltData.uasset
Content/__ExternalActors__/Maps/LVL_Level01_LastShift/...
Content/__ExternalObjects__/Maps/LVL_Level01_LastShift/...
```

Do not commit generated folders such as:

```text
Saved/
Intermediate/
DerivedDataCache/
```

## Done Means

LS-04 is done when:

- `LVL_Level01_LastShift.umap` exists in `Content/Maps`.
- The map opens in Unreal Editor.
- The player can walk through the complete planned route.
- The blockout matches the Level Design document at a rough layout level.
- No gameplay Blueprints beyond the existing template are required.
