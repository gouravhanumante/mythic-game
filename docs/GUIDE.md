# How to work on this game

This is the working agreement. It applies to people and to AI assistants alike; the short version
for AI tools lives in [CLAUDE.md](../CLAUDE.md).

## 1. Starting from a fresh clone

1. Install Unity Hub and Unity 6 LTS, Git and Git LFS (`git lfs install`).
2. Clone the repo and open the folder in Unity Hub.
3. Re-import paid third-party assets from the Asset Store / Package Manager. They live in
   `Assets/ThirdParty/`, which is git-ignored on purpose (license restrictions).
4. Open the scene listed in [PROGRESS.md](PROGRESS.md) and press Play.

## 2. Adding a feature

A "feature" is one player-facing thing: movement, combat, a dummy enemy, a puzzle type, a level.
In order:

1. **Write the feature doc first**: `docs/features/<name>.md` from
   [features/README.md](features/README.md). What the player sees and does, the rules, the
   tuning values. If something is unclear, ask before coding it.
2. **Scripts** go in `Assets/_Project/Scripts/<Feature>/`. Keep one folder per feature.
3. **Scenes and prefabs** go in `Assets/_Project/Scenes/` and `Assets/_Project/Prefabs/`.
   Build the feature as a prefab so it can be reused and tested on its own.
4. **Tuning numbers** (speed, damage, cooldowns) live in `ScriptableObject` assets or serialized
   fields, never hard-coded, so they can be changed without touching code.
5. **Tests**: add Unity Test Framework tests for the rules (see section 4).
6. **Docs**: update the feature doc, [PROGRESS.md](PROGRESS.md), and [TODO.md](TODO.md) for
   anything left out on purpose.
7. Run the checks (section 5).

Prototype with grey boxes first. Art, animation and audio come after the feature feels right.

## 3. Docs: what lives where

Docs describe what the game does **now**, not a history. A doc that contradicts the project is
worse than no doc. **Every change that alters behaviour updates the owning doc in the same commit.**

| If the change touches... | Update |
|---|---|
| A mechanic, a rule, what the player sees or does | `docs/features/<feature>.md` |
| Folder layout, systems, scenes, input, layers, packages | `docs/architecture.md` |
| Setup, versions, build and run steps | `README.md` |
| A feature finished or a gap closed | `docs/PROGRESS.md` and `docs/TODO.md` |
| A known gap, risk or decision deliberately postponed | `docs/TODO.md` (what, why, options) |
| Story, characters, levels, art direction | `docs/design/` |
| How we work | this file |

Before finishing a change:
1. Search `docs/` for the concept you changed (a mechanic name, an input action, a rule), not just
   the script name.
2. Fix anything the change made wrong, and check the sentences around it. Stale text clusters.
3. Point each factual claim at the file or asset that proves it.
4. If the project and a doc disagree and it isn't obvious which is right, ask. Don't silently
   change either.

Don't create a new doc per change. Update the one that owns the topic.

## 4. Tests

- Use the Unity Test Framework: EditMode tests for pure logic (damage, cooldowns, state
  machines), PlayMode tests for behaviour that needs a scene.
- Test a **rule**, stated in plain words first, e.g. "a hit during the dodge's invulnerable window
  deals no damage". Don't assert the implementation back at itself.
- Prove each new test can fail: break the code in the most plausible way, watch the test go red,
  restore it. A test nobody has seen fail proves nothing. If no realistic bug can make it fail,
  it's a regression guard, so say so.
- Keep game logic in plain C# classes where possible, so it can be tested without a scene.

## 5. Checks before committing

1. The Unity Console has no errors (warnings from third-party packages are fine).
2. EditMode and PlayMode tests pass (Window > General > Test Runner).
3. Open the main scene and play it for a minute.
4. `git status` shows `.meta` files alongside every new asset, and nothing from `Library/`,
   `Temp/`, `Logs/`, `UserSettings/` or `Assets/ThirdParty/`.

Don't trust "it compiled". Press Play.

## 6. Commits

- One concern per commit. Code and its docs go together.
- Plain ASCII commit messages (no backticks, no `\u` escapes).
- Commit `.meta` files; they hold asset references and breaking them breaks scenes.
- Large binaries (models, textures, audio, video) go through Git LFS; see `.gitattributes`.
- Never commit paid third-party assets, secrets, keystores or API keys.
- Keep the repo private while it contains anything with a restrictive license.

## 7. Making decisions

For anything with a new package, a new input scheme, a new save format or a new player-facing
control: write down the options and the trade-off, decide, then build. Record the decision in the
feature doc (or `architecture.md` if it is project-wide). If a fix turns out much bigger than it
looked, stop and re-decide rather than pushing through.
