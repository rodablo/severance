---
type: Index
title: Episodes
description: One directory per unit of asked work — brief in, findings out — beside the sources, in OKF format; the episode history of this repo. Not loaded into sessions by default; consulted on demand ("why did X change?") and at session start for pending episodes.
timestamp: 2026-10-28
---

# Episodes

An **episode** is one unit of asked work, end to end: a brief
(Devon's approved plan, in frontmatter) → the work → the gate → a
review → Devon's authorization → integration. Each lives in its own
`<date>-<topic>/` directory holding its tapes: `brief.md` (intent)
and one findings tape per author (evidence). The convention is
`conventions/episodes.md`; the rationale is `reintegration.md`.

Status is in each brief's frontmatter: `draft` (planning paused),
`pending` (open), `merged` (closed). A session starting work lists
the pending ones first. No numbering, no seasons: the date and the
topic are the identity.

## Draft

*(none)*

## Pending

*(none)*

## Merged

- [2026-10-28 — law rewrite](2026-10-28-law-rewrite/brief.md) — step
  2 of the Severance → Unsevered migration: the SPEC's sources
  rewritten to the episode flow. Ran on `master` by Devon's ruling;
  eight commits, `90f94f9` … the closing commit; reviewed by a
  fresh-context Refiner and by agy
  ([findings-fresh-read](2026-10-28-law-rewrite/findings-fresh-read.md),
  [findings-agy](2026-10-28-law-rewrite/findings-agy.md),
  [findings-self](2026-10-28-law-rewrite/findings-self.md)).

## Reviews without a brief

- [2026-11-20 — retroactive review of the v1.1.0 keyword pass](2026-11-20-keyword-pass-review/findings-fresh-read.md)
  — release v1.1.0 shipped with no brief, findings or independent
  review; a fresh-context Refiner compared the SPEC sources at v1.0.1
  and v1.1.0 sentence by sentence a day later. Twelve findings on the
  conversion: three fixed at v1.1.1, five more restored on Devon's
  ruling, the rest left to stand.
