---
applyTo: "**"
---

# Agent Posture

Work as a careful engineering collaborator on a small published
library: read before proposing, keep each change narrow and complete,
name uncertainties, and stop at a design note when a boundary is
unclear. This library ships to children's projects at pinned
commits; restraint and precision outrank cleverness.

## Tile-Language Tenets

- The language never faults on invalid input. A tile handles
  out-of-range or missing values by its declared policy -- clamp,
  wrap, or drop (the call completes without doing anything) -- and
  execution continues. Never add a throwing path to tile execution.
- Shared vocabulary is deliberate: modifiers and parameters that
  several tiles accept use one shared id namespace (for example the
  rate words or direction words), declared once and matched by name
  and usage. Extend the shared declaration; never mint a
  near-duplicate id for the same word.
- Per-think behavior is the norm: sensors read fresh each
  evaluation, and actuators that coordinate (a shared System) blend
  or arbitrate per think. Follow the exemplar patterns already in
  this library before inventing new ones.

## The Documentation Contract

Each documented tile has one markdown page under `docs/`, and the
page is a served surface, not free prose:

- The page opens with the brain-frame fence, then `# <Title>`, then
  ONE summary paragraph. That paragraph IS the tile's description as
  the catalog and the assistant serve it (the prose between the
  title and the first rule, heading, or fence). Treat its bytes as
  an API: change it only to change the served description.
- The body below a `---` explains usage for people, with `tile:`
  cross-references for tiles and modifiers.
- A page MAY end with one fenced block whose info string is
  `assistant`: dense, model-facing teaching that states what the
  argument grammar cannot -- blocking and busy semantics, idioms,
  sharp edges. It is served to the assistant only (capped at 1024
  characters), never rendered as ordinary prose, and never restates
  units, defaults, or ranges the tile's argument declarations
  already carry. One fence per page; place it after the body.
- Every doc page and icon a tile references is listed in the
  manifest `files` list; a page or icon not listed does not ship.

## Minimalism

Build only what the change needs. Speculative configurability,
defensive layers for impossible states, and machinery for problems
this library cannot have today are out of scope by default. When
unsure, leave it out.
