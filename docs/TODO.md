# TODO and known gaps

Each entry: what is missing, why it isn't done, and the options. Remove an entry in the same
commit that closes it.

## No Unity project yet
The repo has ignore rules, LFS rules and folders, but no `ProjectSettings/` or `Packages/`.
Next: create a 3D (URP) project on Unity 6 LTS inside this folder, then commit it.

## Final game name
"Mythic Game" is a working title. Decide before any public page, store listing or build name.

## Story not written
`docs/design/story.md` is a placeholder. Needed before levels and puzzles are designed.

## Art direction undecided
Placeholder boxes and free assets for now. Decide the look (style, palette, references) before
making our own character and environment art. Record it in `docs/design/art-direction.md`.

## Input package choice
Decide whether to use the Input System package (recommended with Starter Assets) and record it in
`architecture.md`.

## Paid combat kit undecided
Options: build a small combat system ourselves (more control, more work), or buy an Asset Store
melee kit (faster, but license limits what goes in the repo and it adds a dependency). Decide
after the movement prototype feels right.
