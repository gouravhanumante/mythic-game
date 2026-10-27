# Rules for anyone changing this project

Full working agreement: [docs/GUIDE.md](docs/GUIDE.md). Architecture: [docs/architecture.md](docs/architecture.md).

## Docs change with the work, in the same commit
A change that alters behaviour and leaves a doc saying the old thing is not finished.

| If the change touches... | Update |
|---|---|
| A mechanic, a rule, what the player sees or does | `docs/features/<feature>.md` |
| Folder layout, systems, scenes, input, layers, packages | `docs/architecture.md` |
| Setup, versions, build and run steps | `README.md` |
| A feature finished, a gap found or closed | `docs/PROGRESS.md` and `docs/TODO.md` |
| Story, characters, levels, art direction | `docs/design/` |

Before committing: search `docs/` for every name and concept you changed; point each factual claim
at the script or asset that proves it; if the project and a doc disagree and it isn't obvious
which is right, ask instead of changing either.

## Intent comes from the user
Order of truth: the user, then plain reasoning about what the game should obviously do, then
docs and project. Never infer intended behaviour from the implementation alone. When unsure, ask.
The user owns the story and creative direction; do not invent story, characters or art direction
without asking. Discuss options before adding a package, save format or new player-facing control.

## Tests
State the rule in plain words, test the rule, and watch the test fail against a plausible bug
before trusting it. A test that can't fail is a regression guard; label it.

## Checks before committing
Unity Console has no errors, EditMode and PlayMode tests pass, the main scene plays, and
`git status` shows `.meta` files with their assets and nothing from `Library/`, `Temp/`, `Logs/`,
`UserSettings/` or `Assets/ThirdParty/`.

## Repo rules
- Plain ASCII commit messages; one concern per commit, code and docs together.
- Large binaries go through Git LFS (see `.gitattributes`).
- Never commit paid third-party assets, secrets or keystores. The repo stays private.
