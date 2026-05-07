# QA Checklist - Last Shift

## Movement

- [ ] Player can move with WASD.
- [ ] Mouse look feels responsive.
- [ ] Player cannot escape the intended playable area.
- [ ] Collision works on walls, doors, and props.

## Interaction Prompts

- [ ] Prompt appears only when looking at interactable objects.
- [ ] Prompt text is readable.
- [ ] Prompt disappears when looking away.
- [ ] Interact input works consistently.

## Fuse Pickup

- [ ] Fuse can be picked up once.
- [ ] Fuse pickup updates `HasFuse`.
- [ ] Fuse disappears or becomes inactive after pickup.
- [ ] Player receives clear feedback.

## Power Activation

- [ ] Power cannot be restored without the fuse.
- [ ] Power can be restored after collecting the fuse.
- [ ] `PowerRestored` updates correctly.
- [ ] Lighting or audio feedback confirms power restoration.

## Terminal Interaction

- [ ] Terminal shows offline feedback before power is restored.
- [ ] Terminal becomes usable after power restoration.
- [ ] Terminal unlocks the control room route.
- [ ] Terminal messages are short and readable.

## Door Locks

- [ ] Locked doors do not open.
- [ ] Locked doors play feedback.
- [ ] Control room door unlocks at the correct time.
- [ ] Door state does not reset incorrectly.

## Ending Sequence

- [ ] Final terminal triggers lockdown once.
- [ ] Doors lock during ending.
- [ ] Alarm audio starts.
- [ ] Lockdown lighting activates.
- [ ] Final entity sound plays behind the player.
- [ ] Level ends with fade, message, or controlled stop.

## Audio Triggers

- [ ] Triggered sounds play at the intended locations.
- [ ] Sounds do not replay too often.
- [ ] Volume is balanced.
- [ ] Important feedback sounds are not masked.

## Lighting Readability

- [ ] Main path is visible.
- [ ] Interactable objects can be found.
- [ ] Dark areas add tension without blocking progress.
- [ ] Ending lighting change is noticeable.

## Navigation Clarity

- [ ] Player can understand where to go next.
- [ ] Side rooms do not feel like dead-end confusion.
- [ ] Signage or light guides the player.
- [ ] Objective sequence is understandable without external instructions.

## Softlock Prevention

- [ ] Player cannot lose the fuse.
- [ ] Player cannot lock themselves out of required rooms.
- [ ] Terminal and door states remain valid after repeated interactions.
- [ ] Ending cannot be skipped into a broken state.

## Build Test

- [ ] Windows build completes.
- [ ] Build launches successfully.
- [ ] Level loads in packaged build.
- [ ] Controls work in packaged build.
- [ ] Ending works in packaged build.

## Screenshot / Video Capture

- [ ] Capture Start Office screenshot.
- [ ] Capture corridor atmosphere screenshot.
- [ ] Capture terminal interaction screenshot.
- [ ] Capture lockdown ending screenshot.
- [ ] Record short full Level 1 walkthrough.
