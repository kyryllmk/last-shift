# Architecture - Last Shift

## Approach

Last Shift should use simple Blueprints for Level 1 unless C++ already exists. The goal is to keep the prototype readable, editable, and finishable.

## Core Blueprint Systems

### BP_PlayerCharacter

Handles first-person movement, camera, line trace interaction checks, and input.

### BPI_Interactable

Interface used by any object the player can interact with.

Recommended functions:
- `CanInteract`
- `GetInteractionText`
- `Interact`

### BP_Door

Basic door actor with locked and unlocked states.

### BP_Fuse

Pickup actor that sets `HasFuse` when collected.

### BP_PowerSwitch

Uses the fuse state to restore facility power.

### BP_Terminal

Displays system text, checks power state, and unlocks the next objective.

### BP_LockdownTrigger

Starts the final Level 1 ending sequence.

### BP_AudioTrigger

Plays one-shot or looping audio cues when the player enters a defined area.

### WBP_InteractionPrompt

Small UI widget that displays the current interaction text.

### WBP_TerminalMessage

Simple terminal message UI for short system feedback.

## Scene / Map Structure

Recommended map name:
- `LVL_Level01_LastShift`

Recommended level sections:
- Start Office
- Main Corridor
- Storage Room
- Fuse Room
- Terminal Area
- Control Room

Keep all Level 1 logic visible and simple. Avoid hidden chains of triggers that are hard to debug.

## Interaction Flow

1. Player camera performs a short line trace.
2. If the hit actor implements `BPI_Interactable`, show `WBP_InteractionPrompt`.
3. Player presses Interact.
4. Player character calls `Interact` on the target actor.
5. Target actor handles its own result and updates game state if needed.

## Game State Variables

Recommended simple variables:

| Variable | Type | Meaning |
| --- | --- | --- |
| `HasFuse` | bool | Player has picked up the fuse |
| `PowerRestored` | bool | Facility power has been restored |
| `TerminalUnlocked` | bool | Terminal can be used after power returns |
| `ControlDoorUnlocked` | bool | Control room door can open |
| `LockdownTriggered` | bool | Final ending sequence has started |

For Level 1, these can live in a simple game state Blueprint, level Blueprint, or manager actor. Prefer the simplest option that remains easy to inspect.

## Fuse Logic

1. Player interacts with `BP_Fuse`.
2. Set `HasFuse = true`.
3. Hide or destroy the fuse pickup.
4. Show short feedback such as "Fuse collected."

## Power Logic

1. Player interacts with `BP_PowerSwitch`.
2. If `HasFuse = false`, show feedback that a fuse is missing.
3. If `HasFuse = true`, set `PowerRestored = true`.
4. Enable terminal interaction.
5. Trigger power-up lighting and audio changes.

## Terminal Logic

1. Player interacts with `BP_Terminal`.
2. If `PowerRestored = false`, show an offline message.
3. If `PowerRestored = true`, set `TerminalUnlocked = true`.
4. Display a short system message.
5. Unlock the control room door.

## Door Unlock Logic

1. `BP_Door` checks its locked state when interacted with.
2. Control room door uses `ControlDoorUnlocked`.
3. If locked, play locked sound and show prompt.
4. If unlocked, open normally.

## Ending Sequence Flow

1. Player enters control room.
2. Player activates final terminal.
3. Set `LockdownTriggered = true`.
4. Lock doors.
5. Switch to alarm lighting.
6. Play lockdown alarm and heavy door sounds.
7. Play final entity sound behind player.
8. Fade to black or show ending message.

## Scope Guardrails

- Do not add inventory UI for one fuse.
- Do not add combat.
- Do not add enemy AI.
- Do not add complex puzzle chains.
- Do not add save/load until Level 1 is complete.
