# Roadmap - Last Shift

## Phase 0 - Foundation

Objective: Create the repository foundation, documentation, and project plan.

Why it matters: A clear foundation prevents scope creep and makes the project readable for portfolio reviewers.

Key outputs:
- Unreal-style folder structure
- README
- Planning documents
- Issue backlog

Done means: The repository is organized, documented, and ready for Unreal project creation or asset work.

## Phase 1 - Level Blockout

Objective: Build a simple Level 1 layout.

Why it matters: The project depends on a readable, finishable space before detailed systems or art.

Key outputs:
- Start Office
- Main Corridor
- Storage Room
- Fuse Room
- Terminal Area
- Control Room

Done means: The player can walk through the full intended route in Play in Editor.

## Phase 2 - Core Interaction Systems

Objective: Implement the minimum Blueprint interaction framework.

Why it matters: Every gameplay objective uses simple interactable objects.

Key outputs:
- Interaction prompt
- Interactable interface
- Basic doors
- Fuse pickup

Done means: The player can look at objects, see prompts, and interact with them.

## Phase 3 - Gameplay Loop

Objective: Connect the fuse, power, terminal, and door objectives.

Why it matters: This turns the blockout into a playable prototype.

Key outputs:
- Fuse state
- Power state
- Terminal state
- Control room unlock

Done means: The full core loop can be completed from start to ending trigger.

## Phase 4 - Story & Environment

Objective: Add narrative context through the level.

Why it matters: The horror tone comes from implication, not complex systems.

Key outputs:
- Warning notes
- Terminal messages
- Abandoned office details
- Facility damage hints

Done means: The player understands that something is wrong without needing cutscenes.

## Phase 5 - Lighting & Audio

Objective: Add the first atmosphere pass.

Why it matters: Lighting and sound carry most of the horror experience.

Key outputs:
- Low-key industrial lighting
- Ambient hum
- Distant metal sounds
- Door and terminal SFX
- Lockdown alarms

Done means: The level is readable, tense, and no longer feels like a plain blockout.

## Phase 6 - Ending Sequence

Objective: Implement the Level 1 lockdown ending.

Why it matters: A clear ending makes the prototype feel complete.

Key outputs:
- Final terminal activation
- Alarm and lighting change
- Door lock feedback
- Entity sound behind player
- Fade or end screen

Done means: Activating the final terminal reliably ends the level.

## Phase 7 - Polish, QA & Build

Objective: Stabilize the prototype and prepare portfolio materials.

Why it matters: A small polished build is stronger than a large unfinished one.

Key outputs:
- QA pass
- Windows build
- Screenshots
- Gameplay video
- README polish

Done means: The project can be opened, played, built, and presented on GitHub.

## GitHub Project Workflow

Recommended project columns:
- Backlog
- Ready
- In Progress
- Review
- Done

Daily workflow:

1. Pick one issue.
2. Move it to In Progress.
3. Create a feature branch.
4. Implement only that issue.
5. Commit with a clear message.
6. Push the branch.
7. Merge into `dev`.
8. Move the issue to Done.

## Branching Strategy

- `main` = stable portfolio version
- `dev` = active integration branch
- `feature/*` = single issue work
- `docs/*` = documentation-only work

Branch examples:
- `feature/LS-04-level-blockout`
- `feature/LS-12-fuse-pickup`
- `feature/LS-20-lockdown-ending`
- `docs/LS-03-readme-polish`

## Commit Convention

Format:

```text
type(scope): message
```

Types:
- `feat`
- `fix`
- `docs`
- `audio`
- `level`
- `ui`
- `refactor`
- `build`
- `test`

Examples:
- `docs(readme): add project overview and roadmap`
- `level(blockout): create first pass of level one layout`
- `feat(interaction): add interactable interface`
- `feat(fuse): implement fuse pickup state`
- `feat(terminal): add lockdown terminal interaction`
- `audio(ambience): add facility background hum plan`
- `fix(door): correct locked state logic`
- `ui(prompt): add interaction prompt widget`
- `build(windows): prepare first playable build`
- `docs(qa): add level one testing checklist`

## First 7-Day Execution Plan

### Day 1 - Project Foundation and Documentation

Primary objective: Set up the repository and planning docs.

Exact outputs:
- Folder structure
- README
- Roadmap
- GDD
- Issue backlog

Done means: The project has a clear development plan before implementation starts.

### Day 2 - Level 1 Blockout

Primary objective: Create the first playable spatial layout.

Exact outputs:
- Office, corridor, side rooms, terminal area, and control room blockout
- Basic player start
- Clear route through the level

Done means: The player can walk the intended path from start to control room area.

### Day 3 - Interaction System and Doors

Primary objective: Add the simplest reusable interaction foundation.

Exact outputs:
- Interactable interface
- Interaction prompt widget
- Basic locked/unlocked door Blueprint

Done means: The player can interact with doors and receive clear feedback.

### Day 4 - Fuse, Power, and Terminal Loop

Primary objective: Connect the core objective chain.

Exact outputs:
- Fuse pickup
- Power switch or fuse box
- Terminal unlock state
- Control room door unlock condition

Done means: The main gameplay loop works from fuse pickup to control room unlock.

### Day 5 - Story Props, Notes, and Environmental Hints

Primary objective: Add narrative context without expanding scope.

Exact outputs:
- Notes
- Terminal messages
- Abandoned workspace props
- Damage and warning hints

Done means: The player understands the evacuation and facility danger through the environment.

### Day 6 - Lighting, Audio, and Ending Sequence

Primary objective: Make the level feel like horror and add the ending.

Exact outputs:
- First lighting pass
- Ambient audio
- Triggered sounds
- Lockdown ending sequence

Done means: The level has a complete beginning-to-ending experience.

### Day 7 - QA, Polish, Screenshots, Build

Primary objective: Prepare a stable portfolio-ready prototype.

Exact outputs:
- QA checklist pass
- Bug fixes
- Windows build
- Screenshots
- Short gameplay capture

Done means: The prototype can be shared and presented clearly.
