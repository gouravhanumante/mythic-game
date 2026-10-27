# Combat

Status: planned · Scripts: `Assets/_Project/Scripts/Combat/` and `Enemies/` (not created yet)
Scene / prefab: Sandbox scene, Dummy enemy prefab (not created yet)

## What it is for
The player can fight with simple melee: attack, dodge and later block. The first version only
needs to feel good against one training dummy.

## What the player sees and does
- Attack button swings; repeated presses chain into a short combo.
- Dodge button moves the player quickly in the movement direction.
- A dummy enemy takes damage and shows it (flash, sound, health bar).

Mechanics are our own implementation of common action-game ideas; no code or assets are copied
from other games.

## Rules
To be written with the first implementation. Examples of the kind of rule expected:
- A hit during the dodge's invulnerable window deals no damage.
- An enemy at zero health cannot be damaged again.

## Tuning
| Value | Where it lives | Default |
|---|---|---|
| Damage, attack cooldown, dodge distance, invulnerable time | To be decided | To be decided |

## Platform / input differences
Same as movement; bindings recorded in `architecture.md` once the Input System is set up.

## Not done yet
Everything. Combat kit vs own system is an open decision in [TODO.md](../TODO.md).
