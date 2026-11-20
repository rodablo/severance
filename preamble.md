# SEVERANCE (SPEC) — the Unsevered workflow

**Severance** is a workflow for running AI coding-agent sessions
against one shared repository, across time and across lanes, without
any of them trampling the others or the truth. Its second form,
**Unsevered**, rests on one idea: every session ends and the next one
wakes with no memory of it, so **the repo carries the continuity** —
every unit of work leaves a brief, findings and commits that the next
session reads first. Work happens in **episodes**: Devon approves a
plan; the plan becomes a brief; Refiners implement on a branch; Mark
runs the gate and obtains a review; Devon authorizes; Mark integrates
with a plain merge. This document is the **binding law**; a consumer
project obeys it plus its own `profile.md` (see "The profile
contract", last section). The law is agent-vendor-neutral: it assumes
only sessions that read a repo, hold private memory, load configured
context, and can spawn agents — it has been used with Claude Code and
Antigravity.

This artifact is generated — it MUST NOT be edited; edit the sources
in the Severance repo and re-release. Links in it MUST be absolute: it
is read from vendored locations where repo-relative paths are dead.

**Normative keywords (BCP 14 — IETF RFC 2119, RFC 8174).** The key words
`MUST`, `MUST NOT`, `REQUIRED`, `SHALL`, `SHALL NOT`, `SHOULD`,
`SHOULD NOT`, `RECOMMENDED`, `NOT RECOMMENDED`, `MAY`, and `OPTIONAL` in
this document are to be interpreted as described in BCP 14 (RFC 2119,
RFC 8174) when, and only when, they appear in ALL CAPS, as shown here.
Lowercase forms retain their ordinary English meaning. See "Epistemic
voice by document type" below for how OKF document types govern voice
across a consumer repository.

## The cast (working vocabulary — used throughout this law)

| Name | Is | Descriptive form (also valid) |
|---|---|---|
| **Devon** | the user — the sole authorizer | "the user" |
| **Mark** | the main session, as one worker across sessions and lanes | "the main session" |
| **Refiners** | agents a session spawns (worktree implementers, read-only reviewers, probes) | "agents" |
| **tapes** | the single-author files of an episode: the **brief** and the **findings** | "the episode's files" |
| **episode** | one unit of asked work: brief → branch → gate → review → merge | "a unit of work" |

Casing rule: docs and agent-directed text MUST write the cast names
(Devon, Mark, Refiners) capitalized, and the working nouns (episode,
tapes, brief, findings) lowercase; lowercase cast names are accepted
only when Devon types them and MUST NOT be written back. The names' story, and the anti-overstretch
principle governing them, live in the RECORD — the companion
narrative artifact, `RECORD.md` (`conceit.md` upstream) — law here,
lore there. Generic names used in this law's examples:
**Lumon** = the generic company, **Cold Harbor** = the generic consumer
project (doc-only terms; they never name a real filesystem path).

## Adoption, in brief

1. Vendor this file into your repo (commit the copy; its `version`
   frontmatter is your pin; update = replace file, diff, commit).
2. Write `profile.md` beside it answering the profile contract —
   including one entry per lane you work in.
3. Load this file into every session's context via each harness's
   auto-loaded configuration (e.g. `CLAUDE.md`, `AGENTS.md`); keep the
   RECORD out of session context — it is for humans.
4. Create `episodes/` at the repo root with an `index.md` (episodes
   convention). On any checkout worked on locally, set the harness to
   branch Refiners from the local HEAD (Claude Code:
   `worktree.baseRef: "head"`), or push before spawning — by default
   they branch from the remote and cannot see unpushed commits.
