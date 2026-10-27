# Mythic Game (working title)

A third-person action-adventure PC game inspired by Indian mythology, built solo with AI assistance in Unity.

## Status
Phase 1: prototype. One grey-box room, a controllable character, then basic combat.

## Tech
- Engine: Unity 6 LTS (3D URP template)
- Language: C#
- Version control: Git + Git LFS (large art/audio files)

## Roadmap
1. Room + moving character (Starter Assets Third Person Controller)
2. Attack, dodge, and one dummy enemy
3. Mixamo animations for combat
4. Our own character and environment art
5. First complete level (combat, puzzle, audio, story intro)

## Setup on a new machine
1. Install Unity Hub and Unity 6 LTS
2. Install Git and Git LFS (`git lfs install`)
3. Clone this repo and open the folder in Unity Hub
4. Re-import any paid assets from the Asset Store (they are not stored in this repo)

## Folder conventions
- `Assets/_Project/Scripts` our own code
- `Assets/_Project/Scenes` scenes
- `Assets/_Project/Art` our own art and animation
- `Assets/_Project/Audio` our own audio
- `Assets/ThirdParty` imported packs (git-ignored)
- `docs/` working docs (see below)
- `CLAUDE.md` short rules for AI assistants

## Docs
Docs describe what the game does now and are updated in the same commit as the change.

| Doc | What it holds |
|---|---|
| [docs/GUIDE.md](docs/GUIDE.md) | How we work: adding a feature, tests, checks, commits |
| [docs/architecture.md](docs/architecture.md) | Folder layout, systems, scenes, input, dependency rules |
| [docs/PROGRESS.md](docs/PROGRESS.md) | What is built and verified |
| [docs/TODO.md](docs/TODO.md) | Known gaps and postponed decisions |
| [docs/features/](docs/features/README.md) | One doc per feature, written before the code |
| [docs/design/](docs/design/README.md) | Story, art direction, level plans |
