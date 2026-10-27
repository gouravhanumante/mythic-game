# Feature docs

One file per feature: `docs/features/<feature>.md`. Write it before the code, keep it true
after. It describes what the feature does now, not how it got there. A feature that is not built
yet says so at the top.

## Template

```markdown
# <Feature name>

Status: planned | in progress | built · Scripts: `Assets/_Project/Scripts/<Feature>/`
Scene / prefab: `<path>`

## What it is for
One or two sentences, in the player's words.

## What the player sees and does
Controls, feedback (animation, sound, UI), and how it feels.

## Rules
Plain sentences a test can check, each pointing at the script and the test:
- <rule> — `<File.cs>`, tested by `<TestClass.TestName>`

## Tuning
| Value | Where it lives | Default |
|---|---|---|

## Platform / input differences
Keyboard + mouse vs controller, anything that behaves differently, and why.

## Not done yet
Link to the docs/TODO.md entries for this feature.
```

## Features

| Feature | Doc |
|---|---|
| Player movement | [player-movement.md](player-movement.md) |
| Combat | [combat.md](combat.md) |
