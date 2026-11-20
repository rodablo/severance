# Trace notes on removal

When a change **removes or abandons a non-trivial, design-bearing
mechanism**, the same change MUST **leave — or update — a trace note**
in the consumer's knowledge tree. A *trace* is the preserved evidence of
something that no longer exists in the code: enough of the lost design
to revisit the decision later without re-deriving it from scratch.

## When it applies

Design-bearing removals only:

- a mechanism, macro, or module retired in favour of a survivor,
- a build target or pathway,
- project tooling,
- an approach abandoned in favour of an alternative.

It does **not** apply to routine deletions — dead lines, stale comments,
trailing whitespace, mechanical refactor fallout with no design content
behind it. Do not demand a note for every deleted hunk.

## What the note must capture

A trace note MUST capture what git history can't — history preserves
the **bytes**, not the **why**:

1. **The lost design's mechanics** — concrete enough to resurrect it.
2. **Why it lost** — and whether the decision was *conditional* ("the
   survivor works in every scenario today while this path is actively
   broken") or *on the merits*. A conditional loss is an open invitation
   to revisit; say so.
3. **What would justify revisiting** — the trigger that should reopen
   the trade-off.

Updating an existing note MAY satisfy this rule — when a removal
completes or extends a story an existing note already tells, the author
SHOULD extend that note rather than creating a near-duplicate file.

## Why

This convention is what makes "just delete it — git history already
preserves it" review guidance actually safe: deletion is cheap only when
the rationale survives somewhere findable.
