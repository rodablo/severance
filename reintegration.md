# Mark reintegration — the journey to an unsevered workflow

**Status: PRELIMINARY DESIGN RECORD.** Drafted 2026-10-28 by the
session running in the bare-local lane (Claude, `claude-fable-5-1`,
with a stretch on `claude-opus-5-5`), distilling a day-long design
conversation with Devon. It is the migration's brief: every item
below carries a status — *decided* (Devon ruled), *leaning* (Devon's
stated inclination, not a ruling), *hypothesis* (agreed shape, untested
in use), *verified* / *documented* (evidence named), *open*. Nothing
here is law yet; the law is rewritten from this record in a later
episode.

## Why

Severance's founding premise — isolate the inner session in a
container and legislate the channel between the two — has **lost
priority**. Three facts moved it (Devon, 2026-10-28):

1. **Sandboxes exist now**, in both harnesses in use: Claude Code's
   per-command bubblewrap sandbox and Antigravity's per-command
   namespace sandbox. Machine protection no longer needs a container.
2. **Claude Code on the web runs in an Anthropic-managed VM** with
   nothing of the user's on it but the clone. It is the *strongest*
   isolation available — and the lane the devcontainer obstructed.
   This inversion is an important motivation of the move.
3. **Severance's learnings were valuable** and must carry forward
   whole: the register, the trace notes, the release discipline, the
   probe-before-believing rule, the provenance habit.

What the container gave was two things, not one: *isolation* (now
covered by sandboxes and the VM) and *separation of duties* (draft vs
apply/verify through an auditable channel). The second does not come
with a sandbox; the new workflow carries it by other means.

## The name and the reading (decided)

- **Unsevered** is the successor workflow's name. The repo stays
  `tekii/severance`; the Severance name is kept as homage to the
  workflow's beginnings. (2026-11-01: the repo moved to the user's
  personal account; the name is unchanged.)
- **Reading 2 — continuity is the point.** The name does not merely
  say "the boundary is gone"; it says every session inherits a
  continuous shared memory *from the repo*. The remaining severance is
  temporal — between one session and the next — and the record is the
  only thing that crosses it.
- **Reintegration** names *this migration* (Severance → Unsevered),
  not a mechanism of the workflow. In the show it is a one-time
  procedure, attempted, partial, risky, unfinished; ours is sanctioned,
  and only as complete as what Severance wrote down.
- **Objective:** align the workflow to the tools and idiosyncrasies of
  **Claude Code and Antigravity (agy)**, with official guidance taken
  as inspiration, never influence.

## Cast (decided)

| Name | Meaning |
|---|---|
| **Devon** | the user: the only real-time continuous memory and the sole authorizer — approves plans, authorizes integrations and pushes. The repo now shares the continuity job. |
| **Mark** | the main-session *lineage*: the one worker whose memory is severed at every session end and restored from the record at every session start. A session is one of Mark's days. Model-neutral: a Claude or agy main session reading the same record is the same Mark. Mark plans, briefs, runs the gate, integrates. |
| **Refiners** | spawned implementer agents, each in an isolated worktree on its own branch, briefed with the law injected verbatim, torn down afterwards. Never restored themselves; their findings are. |
| **Lumon / Cold Harbor** | unchanged: the generic company / consumer project, doc-only. |

**Retired as working vocabulary:** Outie, Innie, the severed floor and
the outside. They name the host/container split, which no longer
exists; they survive in the RECORD as history. Rejected on the record:
re-mapping Innie to the implementer or to forked subagents (true, but
redundant with Refiners and an overstretch). The reviewer, the main
session and the episode keep plain names — the anti-overstretch rule.

Conceit deltas to own in the rewrite: the split is temporal, not
spatial; the show's reintegration fails where ours is a ritual;
"episode" and "brief" were chosen on plain-English merits and only
then found to be show vocabulary (Cold Harbor is an episode title; the
show's Mark leads MDR) — coincidences, never rules. **No numbering,
seasons or arcs** for episodes: date and topic are the identity.

## Vocabulary (decided unless marked)

| Term | Meaning |
|---|---|
| **episode** | one unit of asked work, end to end: brief → implementation on a branch → gate → review → authorization → merge. *The episode is the branch.* |
| **episodes/** | the folder at the repo root — **beside** `knowledge/`, in vendor and consumer alike — holding one `<date>-<topic>/` directory per episode, OKF frontmatter, its own `index.md`, a pointer from the consumer's `knowledge/index.md`. Kept out of the default session load. |
| **tape** | the genre: a single-author, provenance-headed file inside an episode. Once erased after viewing; now kept. (accepted with "brief") |
| **brief** | the intent-side tape: the approved plan wrapped in frontmatter, committed as the branch's first commit, injected verbatim into the Refiner. Requirements, constraints, decisions and acceptance checks — the solution prescribed only where load-bearing. |
| **findings** | the evidence-side tape: the review verdict and/or implementer report, committed on the branch. ("debrief" remains available.) (accepted with "brief") |
| **plan** | the pre-approval proposal made in plan mode and approved by Devon — the native form of "passing the camcorder". Lane-local until it becomes a brief. |
| **gate** | the consumer's mechanical check (`make test` in Cold Harbor; `make check` here). Run by Mark on the exact merge candidate; a relayed "it passed" is never acted on. |
| **reviewer** | an unanchored reader of the diff — a fresh agent or another model — briefed without Mark's conclusions. |
| **lane** | a place a session runs: web (VM), devcontainer (container), bare local (sandbox), agy (sandbox). Declaration-only; the technical term is always the working term, "boundary" the abstract word. |
| **status** | frontmatter field on a tape: `draft` / `pending` / `merged`, flipped by the merge. An open branch with a brief and no merge *is* a pending episode. (hypothesis) |

## Lanes and their boundaries (decided: three lanes, none nested)

| Lane | Boundary | Reach | Notes |
|---|---|---|---|
| **Web** | Anthropic's VM (runs as root; nothing of the user's on it) | the clone only | strongest isolation; project hooks fire; GitHub write tools present — Rule 7 is the only brake |
| **Devcontainer** (VS Code) | Docker: firewall, non-root, pinned toolchain, own `~/.claude` volume | browser/visual verification (Playwright + Chromium proven), pinned build | the **verification lane** for Cold Harbor; *leaning B:* its own clone in a container volume |
| **Bare local** | bubblewrap (`claude-bwrap`), per command; file tools run outside it | credentials, publish, push, the other model, cross-repo evidence, the user's terminal | the **host-operations lane**; accidental-scope threat model; keeps tool profiles + deny rules |
| **agy** (Antigravity CLI, native Linux) | per-command namespace sandbox, **no network**, repos mounted read-only | the other model | *working assumption:* auditor + publisher, never author |

Rules that fall out:
- **No sandbox inside the container** (decided): the container is the
  boundary, same shape as the VM; nesting is blocked by Docker's
  defaults anyway.
- **Rule 7 — push is user-authorized — is lane-independent** (decided),
  enforced by whatever each lane has: the tracked `ask` on `git push`
  (bare local), bypass approval (agy), VS Code's forwarded host
  credentials plus the law (devcontainer), the law alone (web).
- **The isolation clause of the law is per lane; everything else is
  written once.**
- A fifth lane in GitHub Codespaces is a parked, low-priority fallback
  for browser work on the cloud side (Cold Harbor's July survey found
  the devcontainer transfers there).

## Roles and the episode flow (decided shape; mechanics hypothesis)

1. **Plan** — Mark and Devon shape the work in plan mode. Devon
   approves (editable first). The plan is a harness file in the home
   directory: lane-local until step 2.
2. **Brief** — the approved plan, wrapped in OKF frontmatter, lands at
   `episodes/<date>-<topic>/brief.md` and is committed as the branch's
   first commit. The brief is a *derived* artifact; the harness never
   writes it to the repo. A plan paused for longer than a session is
   committed early with `status: draft`.
3. **Implement** — Refiners work in isolated worktrees on the episode
   branch, briefed verbatim. Several Refiners on one brief partition it
   by *disjoint file sets* (Cold Harbor's rule: cross-cutting refactors
   stay atomic on one branch). Requirements-level briefs are the
   default; verbatim prescription where mechanics are load-bearing, and
   for prose where Mark is the author.
4. **Gate** — Mark runs the gate on the exact merge candidate.
5. **Review** — an unanchored reviewer (a fresh agent, or agy) reads
   the diff and writes `findings.md`, committed on the branch (by Mark
   when the reviewer is agy, with dual attribution). Mark verifies the
   reviewer's citations before acting on them.
6. **Fix, gate again** — further commits on the branch.
7. **Authorize** — Devon authorizes the integration.
8. **Integrate** — Mark merges with a **plain merge commit, no squash**
   (decided). The merge commit carries the gate result and the
   authorization: the successor of the tape's `Trigger:` line. A
   Refiner may tidy its own work-in-progress inside the branch before
   review; the rule binds the integration step only.

Reading modes: `git log --first-parent master` is the episode history;
plain `git log` is the commit grain, with every author's
`Assisted-By:` intact. Cold Harbor already merges this way.

Who holds what: Refiners implement (decided); Mark gates and
integrates (leaning: "the true candidate"); the reviewer is unanchored
(decided); Devon authorizes (decided).

## Provenance and continuity (definitions pinned)

- **Provenance** is backward-looking and append-only: for any change,
  who asked, who did it, what was checked and how, who authorized,
  what was learned. Severance recorded it per commit (`Assisted-By:`),
  per idea (the register), per removal (trace notes) — and the
  per-*episode* layer lived in tapes designed to be erased. The branch
  gives that layer a durable home. **Devon's ruling: provenance proved
  of great value; keep and extend it.**
- **Continuity** is forward-looking and current: what the next
  session, in any lane and on any model, needs to act without
  guessing. It is rewritten as state moves; a stale continuity artifact
  is harmful. It lives in the clone — never in a session's memory,
  which is a same-Mark-same-machine convenience.
- **Durable** means: survives the transcript *and* lives in the clone.
  Harness mailboxes, plan files and private memory are relays, not
  records.
- Rule candidates: a continuity artifact says how to verify itself;
  whatever is needed to continue is committed on the episode branch
  before the session ends.

## What retires, what survives (confirmed against Cold Harbor's notes)

Cold Harbor's own `parallel-agent-worktrees.md` called its hooks the
fallback for keeping the bind-mount and named "capability removal
(RO-mount / own clone)" as the stronger option. Option B *is* that
option. Under it:

| Obsolete | Survives |
|---|---|
| `guard-main-head.sh` PreToolUse deny; `reference-transaction` and `post-checkout` hooks; the `findmnt` precondition; the Makefile volume refusal; the `TEPPAN_BUILD` named volume as isolation; `TEPPAN_IN_CONTAINER` as a guard key; the container's `bypassPermissions` workaround; bind-mount hygiene; `.handoff/` on the mount, Rule 3, the shared-mount side-channels; `mdr.sh` (replaced by native Refiners, not by B) | the container's firewall, non-root user and pins; the `~/.claude` config volume (never shared with the host — verified in `devcontainer.json`); Playwright; the gate, register, trace notes, attribution and path hygiene; Rule 7 |

Each retirement wants a trace note and a register entry: *policing
replaced by capability removal.*

Two hazards survive B and need a rule: concurrent sessions within one
clone (the main checkout is reachable from every Refiner — see
verification), and the host checkout shared today by bare-local Claude
and agy. **Rule candidate: one Mark per checkout at a time; a second
concurrent session works in a worktree.** agy's auditor role needs no
clone of its own *provided it never receives a `.git` write grant*.

## Antigravity (agy) — working assumption

Surveyed 2026-10-28 by the agy session itself on Devon's relay
(native-Linux CLI 1.4.8 → 1.4.9 self-updated at launch; Gemini 4
Argon). It has the same three-topology toolkit as Claude Code —
subagents with worktree isolation, messaging, headless runs, plan
artifacts in the home directory, hooks, read-only modes — so the law
can be written once with a thin per-harness profile (law surface
`AGENTS.md`/`GEMINI.md`, hook file, sandbox grants). Its sandbox has
no network; selective egress exists in the engine (a CEL host
allowlist behind a MITM proxy) but is unreachable from the standalone
CLI today. **Roles:** auditor (cross-model reviewer) and publisher
(Cold Harbor's site deploys under per-deploy approval); never an
author. Findings reach the branch by agy writing the file and Mark
committing it — the mechanics are deferred ("a tomorrow problem").
**Finding to carry:** across two surveys agy's mechanism claims held
up under spot-check while its *attributed quotes* were fabricated three
times — a self-reported VERIFIED label is itself a relayed claim.

## Verification (2026-10-28)

| Claim | Status | Evidence |
|---|---|---|
| Subagents inherit the parent's sandbox | **verified** | probe: `claude-bwrap (enforce)`, `Seccomp: 2`, `$HOME` read-only, identical to the main session |
| Worktree Refiners: path `.claude/worktrees/agent-<id>/`, branch `worktree-agent-<id>`, locked while running, cleaned up when unchanged | **verified**, local and web | two probes + post-check |
| Refiners branch from `origin/<default>`, not local HEAD | **verified** | local probe missed four unpushed commits; docs: `worktree.baseRef: "head"` fixes it — mandatory for local repos |
| The main-checkout block is a textual check on git commands; shell writes into the main checkout go through | **verified**, local and web | `git -C <main>` refused with the harness message; `touch` into the main checkout succeeded |
| Worktree Refiners work in the web lane identically | **verified** | second web probe (first run was the session probing itself) |
| `plansDirectory`: any settings scope, relative to project root; plan files have no frontmatter and prompt-slug names | **documented + verified locally** | settings reference; four plan files inspected |
| A terminal session cannot move to the cloud; `--teleport` copies cloud→terminal; Remote Control moves nothing | **documented** | web + sessions pages |
| The web VM runs as root, sees only pushed commits, fires project hooks | **verified** | web probe |
| The devcontainer never had the host `~/.claude` | **verified** | `devcontainer.json` config volume |
| VS Code forwards host git credentials into containers | **inferred** | a dry-run push authenticated with no `gh` or token in the container |
| Devcontainer under a volume clone | **verified** (on the evidence shown) | Cold Harbor cloned into a container volume: HEAD == `origin/master`, only tracked `.claude/` content present, fresh config volume, Claude Code and Playwright MCP up, `make test` passing, dry-run push authenticated. Not shown: the `findmnt` source line and build-log mount warnings |
| Browser in the web lane | **optional / low priority** | an old cloud session showed screenshots — identify the tool |
| SPEC token budget after the law rewrite | **measured by `wc -w`; loaded size pending** | `[spec]` sources 3,878 → 4,925 words at the episode's close (an episode convention gained, a channel lost; two audits added definitions and obligations a cold reader needed); ≈ 8.7k tokens by the v0.1.0 ratio (4.6k words → 8.2k loaded), against the design's ≤ ~9k budget — inside, with little headroom. Measure the loaded size in the first consumer session after release; a trim episode is the remedy if it exceeds the budget |

## Register candidates born of this phase

- A self-reported VERIFIED label is itself a relayed claim (agy's
  fabricated proof quotes, twice).
- Policing replaced by capability removal (the B3 guards retired by
  the own-clone option their own note named).
- The tool's build is part of the evidence (the agy self-update at
  launch: surveys produced by 1.4.8 while 1.4.9 sat on disk).
- Worktree isolation is a git boundary, not a write boundary (verified
  in both lanes).
- Sandbox masks appear as phantom untracked files (`?? .claude/loop.md`
  is a `/dev/null` mask, not a file).

## Implementation outline (proposed; Devon chose verify-then-legislate)

0. **This document** → tracked here; the migration's brief.
1. **Experiments** — done except the volume-clone check (Devon's).
2. **Law rewrite** — `constitution.md`, `conceit.md`, a new
   `conventions/episodes.md`, `profile-contract.md` per lane and per
   harness, `preamble.md`, `MANIFEST`; trace notes for every removal;
   **agy audits the rewrite.**
3. **Register** — Devon rules on the candidates above and the pending
   ones.
4. **Release** — major bump, `make release`, `make check`, tag.
5. **Cold Harbor adoption, as episodes** — vendor the SPEC; rewrite
   `profile.md`; create `episodes/`; devcontainer to a volume clone;
   retire the guards and `mdr.sh` with trace notes; fix the Linux form
   of `.agents/hooks.json`; decide `.handoff/`'s fate. Devon bootstraps
   by authorizing the first episode under the new rules explicitly.

## Open

- Devcontainer volume clone (B) — leaning, now verified feasible; the
  bind-mount's fast host-side editing is the thing to watch.
- Integrator = Mark — leaning.
- agy findings → branch mechanics — deferred.
- Which tool rendered screenshots in the old cloud session.
- A `PreToolUse` path guard for Refiners (writes outside the worktree)
  and a `Stop` hook for "state written before stopping" — mechanisms
  noted, not proposed.
- `worktree.baseRef: "head"` as a tracked project setting.
