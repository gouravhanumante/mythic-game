# Player movement

Status: planned · Scripts: `Assets/_Project/Scripts/Player/` (not created yet)
Scene / prefab: Sandbox scene, Player prefab (not created yet)

## What it is for
The player can walk, run and jump around a room from a third-person camera that follows from
behind. It is the base everything else (combat, puzzles) is built on.

## What the player sees and does
- Move with WASD or the left stick; look with the mouse or right stick.
- Run by default or with a modifier, jump with one button.
- The character turns to face the direction it moves.
- The camera follows behind and does not clip through walls.

First version uses a placeholder capsule or the Starter Assets character; our own art replaces it
later.

## Rules
To be written with the first implementation. Examples of the kind of rule expected:
- The player cannot jump while already in the air.
- Movement speed does not depend on frame rate.

## Tuning
| Value | Where it lives | Default |
|---|---|---|
| Walk speed, run speed, jump height, gravity | To be decided | To be decided |

## Platform / input differences
Keyboard + mouse and controller both supported; bindings recorded in `architecture.md` once the
Input System is set up.

## Not done yet
Everything. See [PROGRESS.md](../PROGRESS.md).
