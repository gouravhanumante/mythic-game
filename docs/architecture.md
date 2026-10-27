# Architecture

Status: the Unity project has not been created yet, so this describes the intended structure.
Update each section as it becomes true. See [PROGRESS.md](PROGRESS.md) for what exists.

## Platform and tools

| Item | Choice | Notes |
|---|---|---|
| Engine | Unity 6 LTS, 3D (URP) template | PC first |
| Language | C# | |
| Version control | Git + Git LFS | Large art and audio go through LFS (`.gitattributes`) |
| Input | Unity Input System | Decided when the first controller is added; record it here |
| Character base | Starter Assets: Third Person Controller (free, Unity) | Customised, not forked blindly |
| Animation | Mixamo clips for combat placeholders | Own animation comes later |

## Folder layout

```
Assets/
├── _Project/              our own work; everything here is committed
│   ├── Scripts/<Feature>/ one folder per feature (Player, Combat, Enemies, Puzzles, UI)
│   ├── Scenes/            one scene per level, plus a grey-box sandbox
│   ├── Prefabs/           reusable objects: player, enemies, pickups, puzzle pieces
│   ├── Art/               our own models, textures, materials, animation
│   └── Audio/             our own music, effects, voice
├── ThirdParty/            imported packs; git-ignored (license), re-import per machine
docs/                      working docs, see GUIDE.md
```

`Prefabs/` is created when the first prefab is saved.

## Dependency rules

- Gameplay scripts never reach into another feature's internals. Features talk through small
  interfaces or events (for example `IDamageable`).
- Game logic (damage, cooldowns, state machines) lives in plain C# classes; `MonoBehaviour`s are
  thin wrappers that connect it to the scene. This keeps logic testable.
- Nothing in `_Project` depends on a specific paid asset in `ThirdParty`. If a pack is used,
  wrap it behind our own script so it can be swapped or removed.
- Tuning values live in `ScriptableObject` assets, not in code.

## Scenes

| Scene | Purpose |
|---|---|
| Sandbox (planned) | Grey-box room for the first movement and combat prototype |

Add a row for each scene as it is created.

## Layers and tags

Record physics layers, tags and collision-matrix decisions here when the first combat code needs them.

## Input

Record action maps (Move, Look, Jump, Attack, Dodge, Block...) and default bindings here once the
Input System is set up.
