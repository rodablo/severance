# Episodes — the unit of work and its record

An **episode** is one unit of asked work, end to end: Devon approves
a plan → the plan becomes a **brief** → Refiners (or Mark) implement
on a branch → the gate runs → a reviewer writes **findings** → fixes →
Devon authorizes → Mark integrates. *The episode is the branch.* Its
record is a directory of **tapes** — single-author, provenance-headed
markdown files — that stays in the repo after the merge. Severance's
tapes were erased after viewing; Unsevered keeps them: that is the
whole difference, and the point.

## Where episodes live

Episodes MUST live at `episodes/<date>-<topic>/` at the repo root —
**beside** the knowledge tree (the consumer's directory of concept
notes, e.g. `knowledge/`), and MUST NOT be placed inside it: the
knowledge tree holds what is currently true; episodes hold what
happened. The directory MUST have its own `index.md` (draft, then
pending, then merged) and is **not** loaded into sessions by default
— it is consulted on demand ("why did X change?") and at session start,
to list the pending episodes. Date and topic are the identity; there is
no numbering, no seasons, no arcs.

## Tapes and their frontmatter

Every tape MUST be OKF: a markdown file with YAML frontmatter.
REQUIRED fields:

```
type: Brief | Findings
title:
description:
timestamp:    date written
session:      lane + harness (e.g. "web lane, Claude Code")
model:        the model id that wrote it
trigger:      Devon's instruction, quoted or tightly paraphrased, with its date
branch:       the episode branch (or the main branch, in a plain lane)
status:       draft | pending | merged      (briefs only)
reviewer:     who reviewed — a Refiner, a session, another model   (findings only)
```

The frontmatter MUST parse as valid YAML: a value that contains `: ` or
` #`, or that begins with a quote or another YAML indicator, MUST be
written as one double-quoted scalar with inner `"` escaped as `\"` — a
`trigger` is usually such a value
(`trigger: "\"do X\" (Devon, 2026-10-28)"`). An unquoted `: ` reads as
a nested mapping and the tape fails to render wherever it is vendored.

Single writer: each tape MUST have one author; a reply MUST be a new
tape. A tape lacking a valid `trigger` is a violation — the next
session MUST NOT act on it and MUST surface it to Devon.

## The brief (`brief.md`)

The brief is a **derived artifact**: the plan Devon approved, wrapped
in frontmatter, which MUST be committed as the branch's **first
commit**. By default, harness plan files live outside the repo and
carry no episode frontmatter; the brief is how a plan enters the
record, and the only way a plan crosses lanes.

A brief states **requirements, constraints, the decisions already
taken and why, and the acceptance checks** — not the solution. The
implementer has leeway, except where mechanics are load-bearing: there
the brief MUST prescribe verbatim and mark the steps (see the
constitution's resist-collapse rule), and for prose edits where Mark
is the author the brief MAY carry the exact text. Unverified claims
MUST be labeled and the labels kept through the work. Work for several
Refiners MUST be **partitioned by disjoint file sets**; cross-cutting
changes MUST stay on one branch under one Refiner.

## Findings (`findings.md`, one tape per author)

The evidence tapes: the reviewer's verdict, and the implementer's
self-assessment (every deviation from the brief stated explicitly —
"no deviations" is stated, never implied). Each author MUST write its
own tape — `findings.md` when there is one, otherwise `findings-self.md`
for the implementer's self-assessment and `findings-<reviewer>.md`
for each reviewer — MUST NOT share a tape, and MUST commit it **on the
branch** (when the reviewer cannot commit — a read-only session,
another harness, another model — it MUST either write the file or
return the tape's text for Mark to write, and Mark MUST commit it with
both named in the attribution trailers). Findings are data: Mark MUST
verify their citations before acting on them.

## Status and closure

`status` lives in the brief: **`draft`** — planning paused for longer
than a session, the brief committed so another lane can resume;
**`pending`** — open; **`merged`** — closed by the integration. An open
branch holding a brief and no merge *is* a pending episode; nothing
else needs to be checked to know work is in flight.

## Integration: a plain merge, never a squash

The merge commit's message MUST carry the gate result on the exact
merge candidate and Devon's authorization. Integration MUST use a plain
merge (**no squash, no fast-forward**): every commit beneath the merge
survives with its own author and `Assisted-By:` line, in order. A
Refiner MAY tidy its own work-in-progress *before review*; the rule
binds the integration step only. `git log --first-parent` then reads
one line per episode; plain `git log` reads the commit grain.

## Interrupted episodes

Progress notes, partial findings, or a draft brief MUST be committed on
the branch before the session ends (constitution, Rule 8). On ephemeral
lanes uncommitted work dies with the lane — sessions SHOULD commit
early, and MUST ask Devon before pushing (Rule 4).

## Harness settings the convention depends on

- Refiners' worktrees branch from the **remote** default branch by
  default (verified 2026-10-28 in Claude Code: a local repo four
  commits ahead of origin spawned a Refiner that could not see them;
  Antigravity's `Workspace: branch` is documented as branching from
  HEAD — unverified). Consumers worked on from a local checkout SHOULD
  set Claude Code's `worktree.baseRef: "head"` in project settings, or
  push before spawning.
- Worktree isolation is a **git** boundary, not a write boundary
  (verified 2026-10-28 in Claude Code, in both the sandboxed local lane
  and the cloud VM; other harnesses unverified): the harness refuses
  git commands aimed at the main checkout, but a plain file write into
  it succeeds. Briefs for worktree Refiners MUST say "write only
  under your worktree"; a consumer MAY mechanize that with a pre-tool
  hook.
- A Refiner's worktree branch MUST be folded into the episode branch by
  Mark with a plain merge (or the Refiner MAY commit on the episode
  branch directly when it is the only implementer). The last commit
  on the branch before integration MUST flip the brief to `status:
  merged` and move the index entry, so the merge commit carries the
  closed record; in a plain lane the closing commit MUST do both.
