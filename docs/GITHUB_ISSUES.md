# GitHub Issues Backlog - Last Shift

Use one issue per branch. Keep each issue small enough to finish and test before moving on.

## GitHub Project Columns

- Backlog
- Ready
- In Progress
- Review
- Done

## Daily Workflow

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

## LS-01 - Create Unreal Project and Repository Foundation

Priority: P0
Effort: M
Phase: Phase 0 - Foundation
Goal: Create the base Unreal Engine project and clean repository structure.
Tasks:
- Create or confirm Unreal Engine 5 project.
- Confirm Windows PC target.
- Add standard Content, Config, and docs folders.
- Preserve Unreal-generated files.
Deliverables:
- `.uproject` file when Unreal project is created.
- Clean folder structure.
- Initial Git tracking setup.
Acceptance Criteria:
- Project opens in Unreal Engine 5.
- Folder structure matches the repository plan.
- No generated or user files are deleted.
Dependencies: None

## LS-02 - Add Documentation Folder and Starter Docs

Priority: P0
Effort: M
Phase: Phase 0 - Foundation
Goal: Add the core planning documents needed for development.
Tasks:
- Create docs folder.
- Add GDD, roadmap, architecture, level design, audio, atmosphere, QA, issues, release, changelog, and dev log docs.
- Keep docs beginner-friendly and practical.
Deliverables:
- Complete starter documentation set.
Acceptance Criteria:
- Every planned doc exists.
- Docs are readable on GitHub.
- Scope limits are clear.
Dependencies: LS-01

## LS-03 - Configure README for Portfolio Presentation

Priority: P0
Effort: S
Phase: Phase 0 - Foundation
Goal: Make the repository understandable to recruiters, peers, and future collaborators.
Tasks:
- Add project pitch.
- Add overview, gameplay loop, controls, tech stack, roadmap summary, and placeholders.
- Link relevant docs.
Deliverables:
- Professional README.
Acceptance Criteria:
- README explains what the project is.
- README explains how to open and run the project.
- README includes portfolio placeholders for screenshots and video.
Dependencies: LS-02

## LS-04 - Create Level 1 Blockout Map

Priority: P0
Effort: M
Phase: Phase 1 - Level Blockout
Goal: Create the main playable Level 1 map.
Tasks:
- Create `LVL_Level01_LastShift`.
- Add player start.
- Block out the full route.
- Use simple geometry only.
Deliverables:
- Playable blockout map.
Acceptance Criteria:
- Player can walk through the planned spaces.
- Main route follows the Level Design doc.
- Scale feels reasonable for first-person movement.
Dependencies: LS-01

## LS-05 - Build Start Office Blockout

Priority: P1
Effort: S
Phase: Phase 1 - Level Blockout
Goal: Build the opening office space.
Tasks:
- Add office walls, desks, doorways, and first route.
- Add simple placeholder props.
- Add early objective clue location.
Deliverables:
- Start Office blockout.
Acceptance Criteria:
- Player starts in a readable office.
- Exit direction is clear.
- Room supports the story setup.
Dependencies: LS-04

## LS-06 - Build Main Corridor Blockout

Priority: P1
Effort: S
Phase: Phase 1 - Level Blockout
Goal: Build the main navigation spine.
Tasks:
- Add corridor layout.
- Add connections to side rooms and terminal area.
- Add placeholder signage.
Deliverables:
- Main Corridor blockout.
Acceptance Criteria:
- Corridor connects all required spaces.
- Player can identify main and side paths.
- No collision gaps or confusing dead ends.
Dependencies: LS-04

## LS-07 - Build Storage and Fuse Room Blockout

Priority: P1
Effort: M
Phase: Phase 1 - Level Blockout
Goal: Build the side exploration route for the fuse objective.
Tasks:
- Add storage room.
- Add fuse room.
- Add placeholder shelves, panels, and maintenance objects.
Deliverables:
- Storage Room and Fuse Room blockout.
Acceptance Criteria:
- Player can reach the fuse location.
- Side route feels intentional.
- Room layout does not confuse the main objective.
Dependencies: LS-04, LS-06

## LS-08 - Build Terminal Area and Control Room Blockout

Priority: P1
Effort: M
Phase: Phase 1 - Level Blockout
Goal: Build the final progression spaces.
Tasks:
- Add terminal area.
- Add locked control room route.
- Add final control room terminal location.
Deliverables:
- Terminal Area and Control Room blockout.
Acceptance Criteria:
- Terminal and control room are easy to locate.
- Control room feels like a destination.
- Final terminal has a clear placement.
Dependencies: LS-04, LS-06

## LS-09 - Implement Player Interaction Prompt

Priority: P0
Effort: M
Phase: Phase 2 - Core Interaction Systems
Goal: Show a clear prompt when the player looks at interactable objects.
Tasks:
- Add camera trace from player.
- Detect interactable actors.
- Create `WBP_InteractionPrompt`.
- Show and hide prompt based on target.
Deliverables:
- Working interaction prompt.
Acceptance Criteria:
- Prompt appears for interactables.
- Prompt disappears when looking away.
- Prompt text fits the UI.
Dependencies: LS-10

## LS-10 - Create Interactable Interface

Priority: P0
Effort: S
Phase: Phase 2 - Core Interaction Systems
Goal: Create a simple shared interface for usable objects.
Tasks:
- Create `BPI_Interactable`.
- Add basic functions for text, availability, and interaction.
- Document expected usage.
Deliverables:
- Blueprint interface.
Acceptance Criteria:
- Doors, fuse, switches, and terminals can share the interface.
- Interface remains simple.
Dependencies: LS-01

## LS-11 - Implement Basic Door Blueprint

Priority: P0
Effort: M
Phase: Phase 2 - Core Interaction Systems
Goal: Add a reusable locked/unlocked door.
Tasks:
- Create `BP_Door`.
- Add locked state.
- Add open/close behavior.
- Add feedback for locked interaction.
Deliverables:
- Door Blueprint.
Acceptance Criteria:
- Door opens when unlocked.
- Door refuses interaction when locked.
- Door can be reused in Level 1.
Dependencies: LS-09, LS-10

## LS-12 - Implement Fuse Pickup Blueprint

Priority: P0
Effort: S
Phase: Phase 3 - Gameplay Loop
Goal: Add the fuse pickup required for restoring power.
Tasks:
- Create `BP_Fuse`.
- Set `HasFuse` on pickup.
- Hide or disable pickup after use.
- Add pickup feedback.
Deliverables:
- Fuse pickup Blueprint.
Acceptance Criteria:
- Fuse can only be picked up once.
- Player receives feedback.
- State updates correctly.
Dependencies: LS-09, LS-10

## LS-13 - Implement Power Restoration Logic

Priority: P0
Effort: M
Phase: Phase 3 - Gameplay Loop
Goal: Allow the player to restore power after finding the fuse.
Tasks:
- Create `BP_PowerSwitch` or fuse box.
- Check `HasFuse`.
- Set `PowerRestored`.
- Trigger audio or lighting feedback.
Deliverables:
- Power restoration interaction.
Acceptance Criteria:
- Power cannot be restored without the fuse.
- Power restores after fuse pickup.
- Terminal state updates afterward.
Dependencies: LS-12

## LS-14 - Implement Terminal Interaction Logic

Priority: P0
Effort: M
Phase: Phase 3 - Gameplay Loop
Goal: Add a terminal that responds to power state and unlocks progression.
Tasks:
- Create `BP_Terminal`.
- Create `WBP_TerminalMessage`.
- Show offline message before power.
- Unlock control route after power.
Deliverables:
- Working terminal interaction.
Acceptance Criteria:
- Terminal gives clear feedback.
- Terminal works only after power restoration.
- Terminal unlocks the intended next step.
Dependencies: LS-13

## LS-15 - Implement Control Room Unlock Condition

Priority: P0
Effort: S
Phase: Phase 3 - Gameplay Loop
Goal: Connect the terminal state to the control room door.
Tasks:
- Add `ControlDoorUnlocked` state.
- Link terminal success to door unlock.
- Add door feedback before and after unlock.
Deliverables:
- Working control room door progression.
Acceptance Criteria:
- Control room is locked before terminal success.
- Control room opens after terminal success.
- Door state is stable after repeated interactions.
Dependencies: LS-11, LS-14

## LS-16 - Add Environmental Storytelling Props

Priority: P1
Effort: M
Phase: Phase 4 - Story & Environment
Goal: Add simple props that support the evacuation and facility story.
Tasks:
- Add abandoned office props.
- Add maintenance props.
- Add warning signs.
- Add damage hints.
Deliverables:
- First environmental storytelling pass.
Acceptance Criteria:
- Props support the story.
- Navigation remains clear.
- No room becomes cluttered.
Dependencies: LS-04, LS-05, LS-06, LS-07, LS-08

## LS-17 - Add Warning Notes and Terminal Text

Priority: P1
Effort: S
Phase: Phase 4 - Story & Environment
Goal: Add short readable narrative text.
Tasks:
- Write 3 to 5 short notes.
- Write terminal status messages.
- Add lockdown warning language.
Deliverables:
- Notes and terminal text.
Acceptance Criteria:
- Text is concise.
- Story supports the final twist.
- No large reading walls are required.
Dependencies: LS-14, LS-16

## LS-18 - Add First Lighting Pass

Priority: P1
Effort: M
Phase: Phase 5 - Lighting & Audio
Goal: Make the level readable and atmospheric.
Tasks:
- Add dim office and corridor lighting.
- Add fuse room pre-power darkness.
- Add terminal glow.
- Add lockdown lighting setup.
Deliverables:
- First lighting pass.
Acceptance Criteria:
- Main path is readable.
- Important objects are visible.
- Lighting supports tension.
Dependencies: LS-04

## LS-19 - Add Ambient Audio and Sound Triggers

Priority: P1
Effort: M
Phase: Phase 5 - Lighting & Audio
Goal: Add the first audio atmosphere pass.
Tasks:
- Add ambient loops.
- Add electrical and terminal sounds.
- Add distant metal sound triggers.
- Add door and pickup feedback sounds.
Deliverables:
- Audio trigger pass.
Acceptance Criteria:
- Audio supports each room.
- Important feedback is audible.
- Triggers do not spam.
Dependencies: LS-09, LS-18

## LS-20 - Implement Lockdown Ending Sequence

Priority: P0
Effort: M
Phase: Phase 6 - Ending Sequence
Goal: Add the final Level 1 scripted ending.
Tasks:
- Create final terminal interaction.
- Set `LockdownTriggered`.
- Lock doors.
- Start alarm lighting and audio.
- Play final entity sound.
- Fade or display ending message.
Deliverables:
- Complete Level 1 ending sequence.
Acceptance Criteria:
- Ending triggers once.
- Player understands lockdown occurred.
- Sequence completes without softlock.
Dependencies: LS-15, LS-18, LS-19

## LS-21 - Full Level 1 QA Pass

Priority: P0
Effort: M
Phase: Phase 7 - Polish, QA & Build
Goal: Test the full prototype and fix blocking issues.
Tasks:
- Run through QA checklist.
- Test in Play in Editor.
- Test repeated interactions.
- Fix softlocks and unclear navigation.
Deliverables:
- Completed QA pass.
Acceptance Criteria:
- Full level can be completed reliably.
- No known P0 issues remain.
- QA checklist is updated.
Dependencies: LS-20

## LS-22 - Prepare Build, Screenshots, and Portfolio README Polish

Priority: P0
Effort: M
Phase: Phase 7 - Polish, QA & Build
Goal: Prepare the prototype for sharing.
Tasks:
- Package Windows build.
- Capture screenshots.
- Record short gameplay video.
- Update README with final media and status.
- Update changelog.
Deliverables:
- Portfolio-ready repository and build.
Acceptance Criteria:
- Build launches on Windows.
- README includes screenshots or links.
- Project status is honest and clear.
- Release checklist is complete.
Dependencies: LS-21
