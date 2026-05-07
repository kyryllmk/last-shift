# Game Design Document - Last Shift

## Game Overview

Last Shift is a short first-person atmospheric horror game built in Unreal Engine 5. The prototype focuses on one complete Level 1 experience set inside an old industrial facility after an evacuation.

## Player Fantasy

The player is an ordinary night-shift worker trying to stay calm, restore facility systems, and find a way out after being left behind.

## Target Experience

- Isolated and uneasy
- Clear enough to finish without frustration
- Tense through lighting, sound, and environmental clues
- Short, focused, and portfolio-ready

## Story Setup

The player is repairing equipment in an old part of the facility when an evacuation occurs. By the time they return to the office area, everyone is gone. The facility is dark, systems are offline, and access routes are locked.

The player believes they are restoring systems to escape. In reality, the final terminal triggers full facility lockdown and traps them inside with something dangerous.

## Gameplay Loop

Explore -> Find Fuse -> Restore Power -> Access Terminal -> Unlock Control Room -> Trigger Lockdown Ending

## Core Mechanics

- First-person movement
- Interact prompt
- Inspect or use interactable objects
- Pick up one fuse
- Restore power at a switch or fuse box
- Use terminals after power is restored
- Unlock the control room door
- Trigger a scripted lockdown ending

## Controls

| Action | Input |
| --- | --- |
| Move | WASD |
| Look | Mouse |
| Interact | E |
| Sprint | Shift |
| Crouch | Ctrl |
| Pause | Esc |

## Level Progression

1. Start in the office area.
2. Find that the main route is blocked or unpowered.
3. Explore the side storage room.
4. Locate a fuse.
5. Restore power in the fuse room.
6. Return to the terminal area.
7. Unlock the control room.
8. Activate the final terminal.
9. Lockdown begins and Level 1 ends.

## UI Flow

- Interaction prompt appears when looking at usable objects.
- Pickup text confirms the fuse has been collected.
- Terminal UI displays short system messages.
- Ending message or fade confirms lockdown.

## Win Condition

The player reaches the control room and activates the final terminal, completing Level 1.

## Lose / Fail Conditions

There are no combat fail states in Level 1. Failure should come only from temporary confusion, which level design and UI should minimize.

## Strict Scope Limits

- One playable level
- One fuse objective
- One main terminal objective
- One ending sequence
- Blueprint-only implementation unless C++ already exists
- Windows PC target

## Intentionally Not Included

- Combat
- Complex inventory
- Enemy AI
- Multiplayer
- Procedural generation
- Backend services
- Save system
- Multiple endings
- Full monster reveal
