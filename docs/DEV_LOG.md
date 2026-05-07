# Development Log - Last Shift

## How to Use This Document

Use this document to track meaningful progress, decisions, problems, and solutions during development.

Each entry should be short and focused. Log meaningful progress, not every tiny step. Focus on:
- Decisions
- Problems
- Solutions
- Lessons learned

This is not a messy diary. It is a practical record that can help explain the project during interviews and improve future work.

## Entry Template

## [DATE] - Short Title

### What was done

- Bullet points of completed work

### Why it was done

- Reasoning behind decisions

### Problems encountered

- Bugs, design issues, or confusion

### Solutions

- How problems were solved

### Notes / Learnings

- Key takeaways
- What to improve later

## 2026-05-07 - Project Setup & Planning

### What was done

- Created the initial repository foundation.
- Added Unreal Engine-style folders for content, Blueprints, audio, props, UI, lighting, and docs.
- Drafted the README, GDD, roadmap, architecture plan, QA checklist, and issue backlog.

### Why it was done

- The project needs a clear scope before gameplay implementation starts.
- A small horror prototype is easier to finish when the main loop and Level 1 route are defined early.

### Problems encountered

- The repository did not yet contain a generated Unreal project or `.uproject` file.

### Solutions

- Created documentation and placeholder folders only.
- Left Unreal-generated project creation for the next implementation step.

### Notes / Learnings

- Planning the playable loop first helps prevent unnecessary systems like combat, complex inventory, or AI.

## 2026-05-08 - Level Blockout

### What was done

- Planned a compact Level 1 route from Start Office to Control Room.
- Defined the Main Corridor as the navigation spine.
- Assigned each side room a specific gameplay purpose.

### Why it was done

- The player needs a simple route that supports exploration without becoming confusing.
- A readable blockout will make interaction testing much easier.

### Problems encountered

- Side rooms can easily make a small horror level feel like a maze.

### Solutions

- Kept the main route linear.
- Used the Storage Room and Fuse Room as a short side path tied directly to the power objective.

### Notes / Learnings

- Main path clarity matters more than room count for a short portfolio prototype.

## 2026-05-09 - Interaction System Start

### What was done

- Planned the basic Blueprint interaction architecture.
- Identified `BPI_Interactable`, `BP_PlayerCharacter`, `WBP_InteractionPrompt`, doors, fuse, power switch, and terminal as the first required systems.

### Why it was done

- Most gameplay objects share the same interaction pattern.
- A small interface keeps the project easier to extend without building a complex inventory or puzzle framework.

### Problems encountered

- It is tempting to add extra features before the core loop works.

### Solutions

- Limited the system to one interaction button, one fuse pickup, one power state, and one terminal unlock chain.

### Notes / Learnings

- A reusable interaction interface is enough for Level 1 if object behavior stays simple.

## Technical Decisions

### Blueprint-Only First

Blueprints are the best fit for this prototype because the target systems are simple, visual, and easy to inspect in Unreal Engine. C++ should only be added later if the project grows beyond the Level 1 scope.

### No AI System in Level 1

The entity is suggested through sound, shadows, damage, and logs. This keeps the horror focused on atmosphere and prevents the project from expanding into AI debugging.

### Linear Level Design

The level uses a mostly linear path with one side objective route. This makes the prototype more finishable and helps players understand the objective flow without a quest system.

### One Fuse, One Power Objective

The fuse objective teaches interaction and progression without creating inventory complexity. A single clear objective chain is enough for a short playable demo.
