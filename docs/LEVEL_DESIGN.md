# Level Design - Level 1

## Overview

Level 1 is a compact industrial office and maintenance space. The main path must remain clear. Side rooms should support exploration and story, not confuse the player.

## Simple Top-Down Map

```text
[START OFFICE] -> [MAIN CORRIDOR] -> [TERMINAL AREA] -> [CONTROL ROOM]
                       |
                  [STORAGE ROOM]
                       |
                  [FUSE ROOM]
```

## Start Room / Office

Purpose: Establish the player as a facility worker returning to an empty area.

Gameplay function: Introduce movement, interaction, and the first locked or unpowered objective.

Required objects:
- Player start
- Desk
- Workstation
- Evacuation notice
- Locked exit or blocked route

Visual storytelling:
- Abandoned coffee cup
- Empty chairs
- Flickering monitor
- Emergency notice left behind

Audio cues:
- Low building hum
- Distant ventilation
- Occasional light buzz

Lighting style:
- Dim office lighting with one flickering fixture
- Clear visibility around exits

Player guidance:
- Use light and open doorway framing to point toward the main corridor.

Completion condition:
- Player enters the main corridor.

## Main Corridor

Purpose: Connect all Level 1 spaces and build tension.

Gameplay function: Main navigation spine.

Required objects:
- Doors to office, terminal area, storage room, and control route
- Signage
- Locked control door indicator

Visual storytelling:
- Scuffed floor
- Emergency arrows
- Missing wall panel
- Warning sign for old wing

Audio cues:
- Distant metal impact
- Electrical buzz near damaged panel
- Subtle pipe creaks

Lighting style:
- Longer shadows
- Alternating working and broken lights

Player guidance:
- Keep the terminal area visible down the main route.
- Use signage to label storage and control.

Completion condition:
- Player reaches the terminal area or side route.

## Storage / Side Room

Purpose: Reward exploration and route the player toward the fuse room.

Gameplay function: Side space containing clues and access to fuse objective.

Required objects:
- Shelving
- Crates
- Maintenance note
- Door or opening to fuse room

Visual storytelling:
- Equipment left mid-task
- Old safety posters
- Tool cart
- One broken light

Audio cues:
- Close ventilation
- Box or shelf creak
- Small object rattle

Lighting style:
- Darker corners but readable path
- Practical flashlight-friendly layout if flashlight is added later

Player guidance:
- Place the useful path opposite the entrance.
- Keep the fuse room doorway visually distinct.

Completion condition:
- Player finds the route into the fuse room.

## Fuse Room

Purpose: Provide the first clear objective completion.

Gameplay function: Fuse pickup and power restoration setup.

Required objects:
- Fuse pickup
- Fuse box or power switch
- Electrical panel
- Warning label

Visual storytelling:
- Burn marks
- Open panel
- Maintenance log saying power was isolated

Audio cues:
- Electrical buzzing
- Small spark sound
- Power-up sound after activation

Lighting style:
- Very low light before power
- Slightly improved lighting after power restoration

Player guidance:
- Highlight fuse with a small light or silhouette.
- Place power switch in the same room or near the exit.

Completion condition:
- Player collects fuse and restores power.

## Terminal Area

Purpose: Confirm that restored power changes the facility state.

Gameplay function: Terminal interaction unlocks control room access.

Required objects:
- Terminal
- Locked system message
- Control room door status indicator
- Short log text

Visual storytelling:
- Empty security desk
- Monitor showing evacuation or system error
- Warning about lockdown protocols

Audio cues:
- Terminal beep
- Power hum after restoration
- Distant low impact after terminal unlock

Lighting style:
- Monitor glow
- Cold overhead light
- Strong shadow toward control room door

Player guidance:
- Terminal should be directly visible from the corridor.
- Door feedback should clearly show what changed.

Completion condition:
- Player uses terminal and unlocks the control room.

## Control Room / Ending

Purpose: Deliver the Level 1 twist and finish the prototype.

Gameplay function: Final terminal triggers lockdown.

Required objects:
- Final terminal
- Control panels
- Large window or blocked observation point
- Lockdown lights

Visual storytelling:
- Old incident warning
- Damaged chair or console
- Message implying the system is unsafe

Audio cues:
- Terminal confirmation
- Alarm siren
- Heavy door locks
- Final entity sound behind player

Lighting style:
- Brief power surge
- Red lockdown lighting
- End fade or screen darkening

Player guidance:
- Make the final terminal the obvious interactable.
- Keep the player focused forward until the sound behind them.

Completion condition:
- Player activates terminal and lockdown ending plays.
