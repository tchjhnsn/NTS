# AGENTS.md: NTS

The map of this repository is in `README.md`. Read it first.

- Test: `python3 -m unittest discover -s thrivesight_core/nts -t .`
- Lean: `cd lean && lake build` (toolchain in `lean/lean-toolchain`, no Mathlib).
- This repository does not import Reflect, and Reflect does not import it.
- Never read or print `.env*` files.
