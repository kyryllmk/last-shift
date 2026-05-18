# LS-07 Storage and Fuse Room Blockout Guide

This guide supports LS-07: Build Storage and Fuse Room blockout.

The actual room changes should be made in Unreal Editor inside:

```text
Content/Maps/LVL_Level01_LastShift.umap
```

Do not hand-edit `.umap` files outside Unreal.

## Goal

Build the side exploration route for the fuse objective. The player should leave the Main Corridor, enter Storage, understand that this is a side route, and find the Fuse Room without getting lost.

## Scope For LS-07

Build only the Storage Room and Fuse Room blockout. Do not implement fuse pickup logic, power restoration logic, real UI prompts, audio triggers, final lighting, Marketplace dressing, or final story notes yet.

## Required Outputs

- Storage Room connected to Main Corridor
- Fuse Room connected through or near Storage Room
- Placeholder shelves and crates in Storage
- Placeholder fuse location in Fuse Room
- Placeholder power panel / fuse box location
- Clear return path back to Main Corridor
- Collision-clean walls, floors, and door openings
- Side route that feels intentional, not like a confusing maze

## Layout Intent

Keep the main path clear. Storage and Fuse Room should feel like a short side objective route.

Recommended relationship:

```text
[MAIN CORRIDOR]
      |
[STORAGE ROOM]
      |
 [FUSE ROOM]
```

The player should understand:

1. Storage is optional-looking but important.
2. Fuse Room is the useful end of the side route.
3. Returning to the Main Corridor is easy.

## Suggested Scale

Use the same blockout unit scale as the current map. These are practical targets, not strict measurements.

| Element | Suggested Size |
| --- | --- |
| Storage Room | Medium side room, smaller than office if possible |
| Fuse Room | Small maintenance room |
| Door / opening width | About 2 to 3 blockout units |
| Shelf blockout | About 1 to 2 units deep, placed along walls |
| Crate blockout | About 1 x 1 x 1 or 2 x 2 x 2 units |
| Fuse panel / power panel | About 2 x 1 x 3 units on a wall |
| Walkable clearance | At least 2 units on the main movement path |

Prioritize player movement. If a prop blocks the route or causes snagging, move it to a wall or corner.

## Step-By-Step Unreal Editor Tasks

1. Open `LastShift.uproject`.
2. Open `Content/Maps/LVL_Level01_LastShift`.
3. Save immediately before editing.
4. Locate the Storage Room entrance from the Main Corridor.
5. Confirm the Storage entrance is visible but does not look like the main path.
6. Shape the Storage Room into a readable side room.
7. Add placeholder shelves along one or two walls.
8. Add simple crate/tool cart placeholders without blocking movement.
9. Add a clear doorway or opening from Storage to Fuse Room.
10. Shape the Fuse Room as a smaller maintenance space.
11. Add a placeholder fuse pickup location.
12. Add a placeholder fuse box or power panel location.
13. Add a placeholder warning label or sign near the panel if useful.
14. Confirm the player can return from Fuse Room to Storage and back to Main Corridor.
15. Save the level.

## Storage Room Requirements

The Storage Room should communicate:

- This is a side area.
- It contains maintenance supplies.
- It leads to something useful.

Use placeholder geometry for:

- Shelves
- Crates
- Tool cart
- Maintenance note location
- Door/opening to Fuse Room

Do not overfill the room. Empty walking space is more important than clutter.

## Fuse Room Requirements

The Fuse Room should communicate:

- This is where the first objective will happen later.
- Power equipment belongs here.
- The player has reached the useful end of the side route.

Use placeholder geometry for:

- Fuse pickup spot
- Power panel or fuse box
- Electrical wall panel
- Warning sign placeholder
- Small maintenance floor space

## Player Guidance

Use simple blockout guidance:

- Storage entrance visible from Main Corridor
- Fuse Room doorway visible once inside Storage
- Fuse/panel placeholder placed on the far wall or a readable focal wall
- Return route kept unobstructed
- No extra exits unless they already exist in the planned layout

## What Not To Add Yet

- No working fuse Blueprint
- No inventory state
- No power restoration logic
- No terminal unlock logic
- No final note text
- No final lighting pass
- No audio cues
- No Marketplace decoration pass
- No enemy or chase setup

## Smoke Test Checklist

After editing, press Play in Editor and verify:

- Player can enter Storage from Main Corridor.
- Storage reads as a side room, not the main route.
- Player can identify the path from Storage to Fuse Room.
- Player can reach the placeholder fuse location.
- Player can see the placeholder power panel / fuse box.
- Player can walk around shelves and crates without getting stuck.
- Player can return to Main Corridor easily.
- There are no collision gaps or holes in the room boundaries.
- The side route feels intentional and not maze-like.
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
docs/LS_07_STORAGE_FUSE_ROOM_GUIDE.md
```

Do not commit generated folders:

```text
Saved/
Intermediate/
DerivedDataCache/
```

## Done Means

LS-07 is done when:

- Storage Room exists and connects from Main Corridor.
- Fuse Room exists and connects from Storage or the side route.
- Placeholder shelves, crates, maintenance objects, fuse spot, and power panel exist.
- Player can reach the fuse location.
- Player can return to the Main Corridor.
- The side route does not confuse the main objective path.
- The level still runs in Play in Editor.
