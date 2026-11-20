# NTS

**The Number Theory of the Soul** is a formal model of what a person's inner life is made of. It names 18 elements in 9 categories across three planes (the interior life, the shared world of bodies and events, and the transcendental: the Good and the True). Each element is a prime, so a composite such as an emotion about one's own will is named by the product of its primes, and every composite factors back into the elements it came from.

The model is meant to be tested, not believed. It reads a person's own words in its terms: a model may only quote the words worth asking about and pose open questions, and only the person confirms what is true of them. Agreement between the model's readings and the person's own labels (Cohen's kappa) is the measure of whether it works.

**Status:** research in progress. The element model runs in Python with its tests (`python3 -m unittest discover -s NTS_core/nts -t .`). The Lean model of the structure, scopes and the person's records is kept here but has not been rebuilt in this repository yet. Working papers are listed at [tcjcafe.com/research](https://www.tcjcafe.com/research).

## About this repository

The Number Theory of the Soul: the element table, its Lean model, and the code that read journal entries in its terms. It left Reflect (tchjhnsn/reflect) on 2026-11-11 so the theory can grow on its own. Reflect does not import anything from here, and nothing here imports Reflect.

The history comes from Reflect: every commit that touched these files, kept with its original message, author and date.

## Where things are

| Path | Holds |
|---|---|
| `lean/` | The Lean model: scopes, model outputs, frames, the person's stores and onboarding. `lake exe nts-export` writes the structure export. |
| `NTS_core/nts/` | The element model in Python: `elements.json`, `composites.json`, the table, records, reader and agreement, the reader prompts, fixtures and tests. See its README. |
| `packages/core/src/` | The TypeScript side as it stood in Reflect: the 16 elements and salience readings (`state.ts`), bindings, the structure export (`structure.ts`, `structure.json`), the reader and its prompt, drafts, the soul vault (`soul.ts`, `home.ts`) and grounding (`ground.ts`). |
| `packages/cli/serve.ts` | The local soul screens (`reflect serve`). |
| `web/` | The Postgres binding store, the web reader and the structure sync script. |

## Status

- The Python element model runs here on its own: `python3 -m unittest discover -s NTS_core/nts -t .`
- The TypeScript files still import Reflect modules (the journal, the person, the vault layout) that are not here, so they do not build or run in this repository yet (not built). They are kept as the starting point.
- The Lean model was last built in Reflect; it has not been built in this repository yet.

## Rules

- Never read or print `.env*` files. Refer to secrets by variable name only.
- Agents open draft PRs and merge their own on green CI.
