---
type: Reference
title: "SEVERANCE — experiment record (RECORD)"
description: "The Severance experiment's narrative record — conceit, prior art, learnings register, the reintegration (Severance → Unsevered) and the trace of the retired machinery — built at v1.1.0. For human readers; not loaded into sessions."
tags: [severance, record, experiment]
timestamp: 2026-11-19
version: 1.1.0
built-from: v1.1.0
---

<!-- ═══ source: conceit.md ═══ -->

# The Severance conceit

The workflow is named **Severance**, after the TV show, and its
successor keeps the name as homage: **Unsevered** is what the workflow
became, in the same repo, after the migration this record calls
**reintegration**. The name was earned, not borrowed: in the first
workflow the severance was real — two sessions, host and container,
with private memories architecturally invisible to each other, and a
legislated channel between them. In the second it is still real, but
it runs *across time*: every session ends and the next one wakes with
no memory of it, knowing only what was written in the repo. A
**conceit** is an extended metaphor sustained through a work; this
note tells the story once, so the law doesn't have to.

The central irony survives the migration: the show's severance *hides*
the two selves from each other; ours ends by **writing everything
down** — the sanctioned channel became the record itself.

## Why this project exists (the experiment)

This workflow is the process side of the user's **first attempt at
coding with LLMs** — an experiment. The first consumer project —
**Teppan**, a static-site generator by the company TEKii — was the
driver: a real problem solved with the new technology, and an
important deliverable in its own right, so the experiment had to
succeed on both counts. The work is intended for public presentation
(experiment / paper); the conceit is that publication's **hook** — it
draws readers honestly, because every mapping describes the real
architecture. What each step taught is recorded in the learnings
register (`learnings.md`, this RECORD); how the first workflow became
the second is `reintegration.md`.

## The cast — the story behind the table

The SPEC's preamble carries the working table; the mappings' stories:

- **Devon** (the user) holds the authorizing role because Devon is
  the only participant whose memory is continuous in real time — the
  unsevered ally who, in the show, carries the tapes across the
  threshold. The repo now shares the continuity job; Devon keeps the
  authority.
- **Mark** is the main session — not one session but the *lineage*:
  one worker whose memory is severed at every session end and restored
  from the record at every session start. A session is one of Mark's
  days. The name is model-neutral: a Claude session and a Gemini
  session reading the same record are the same Mark. (Pleasingly, the
  show's Mark leads the Macrodata Refinement floor — a coincidence,
  never a rule.)
- **Refiners** are the agents a session spawns — provisioned to one
  piece of work each, judged by a gate, torn down — the severed floor's
  workers. They are not Mark: they are never restored; their findings
  are.
- **The camcorder / tapes**: in the show the two selves exchange
  recorded messages via a camcorder carried across the threshold by
  the unsevered ally — single author per tape, a reply is a new tape.
  That is still the shape of a **brief** and its **findings**. What
  changed is the ending: the show's recipient erases the tape after
  viewing, and so did the first workflow; Unsevered **keeps every
  tape**, on the branch, in the record. One line of `.gitignore` is
  the whole mechanical difference — and the whole point.
- **Episodes**: the unit of work was named on plain-English merits —
  a brief, a branch, a merge is an *episode of work* — and only then
  found to be the show's own vocabulary (the first workflow's source
  incident, "Cold Harbor", is an episode title). An `episodes/` folder
  reads as an episode guide; the first-parent log reads as the season.
  No numbering, seasons or arcs: date and topic are the identity.
- **Reintegration**: in the show, the procedure that undoes severance —
  attempted, partial, risky, unfinished (one character dies of it; the
  protagonist stays split). Here it names the **migration** from the
  first workflow to the second, once, and nothing inside the workflow.
  It was partial in the honest sense too: only what the first workflow
  wrote down crossed over.

Show-fidelity deltas, owned rather than hidden: the split is temporal
here, not spatial — the show never severs a person across days; the
channel is constituted by the authority itself, not contraband; and
the show's reintegration fails where ours is a sanctioned ritual.

## Retired cast

**Outie** and **Innie** named the host and container sessions of the
first workflow; **MDR** named its agent fleet. The host/container split
is gone — each lane now has its own clone — so the names retired as
working vocabulary and live on in the register and in `severed-era.md`,
the trace of the mechanics they ran. Re-mapping Innie to the
implementer (or to a forked agent, which literally is an innie of its
parent) was considered and rejected: true, but redundant with
Refiners, and an overstretch.

## Lanes (declaration-only)

Sessions run in **lanes** — a cloud VM, a container, a sandboxed host,
another harness. In the conceit a lane is a severed floor of its own;
everywhere else the docs say **VM**, **container**, **sandbox**, and
**boundary** for the abstraction — documentation must be understood
first and enjoyed second.

## Rules of the conceit

- **Casing:** capitalized cast names in docs and agent-directed text;
  lowercase accepted only from Devon's typing, never written back.
  "Unsevered" capitalized when it names the workflow, lowercase as the
  plain adjective.
- **Two tiers:** *working vocabulary* (the cast, tapes, episodes —
  names that aid precision because they name things that had no short
  name) vs *declaration-only* (lanes — where exact technical terms
  already exist and must stay the working terms).
- **Anti-overstretch (binds Devon and every session):** the goal is
  naming things, possibly in a funny way — not maximizing the metaphor.
  Names are mnemonic decoration; the constitution defines the behavior;
  when show fidelity and mechanical truth conflict, mechanical truth
  wins. Every name must also work on its plain-English merits for
  readers who have never seen the show.

## Generic mapping

**Lumon** = the generic company, **Cold Harbor** = the generic consumer
project. Both are **doc-only terms** — they never name a real filesystem
path; if an identifier form is ever forced, use `cold-harbor` or
`cold_harbor`.

<!-- ═══ source: prior-art.md ═══ -->

# Prior art & the name collision

Web search, 2026-07-07 (re-verify before the publication phase):

- **The metaphor is culturally established** — essays mapping Severance
  (the show) onto work/AI memory compartmentalization are plentiful
  (consultancy think-pieces, newsletter essays). This is *good*: it is
  what makes the name a working hook. The claim "Severance is like AI
  memory" is a commonplace and must not be presented as a contribution.
- **The name is already in use in the coding-agent space:** at least one
  existing open-source project uses "Severance" as its title — a
  cross-session memory system for a coding agent. **Title-only use**: no
  show vocabulary in its workflow. Crucially, its thesis is the
  *inverse* of ours: it exists to DEFEAT severance (restore
  cross-session memory), while this project EMBRACES severance as
  architecture and constitutionalizes the channel across it. Position
  the public repo/paper against this collision explicitly — a
  citation-and-contrast footnote (locate the project again at
  publication time) strengthens the contribution claim.
- **No trace found** of the actual move made here: fiction-derived role
  names for concurrent host/container agent sessions, an unsevered
  user-mediator, a single-writer/consumer-deletes tape protocol,
  ephemeral refiner agents. Caveat: web search proves absence of
  *findable* prior art only; a deeper pass is due before publication.

<!-- ═══ source: learnings.md ═══ -->

# Learnings register

What each step of the experiment taught — governed by the
learnings-register convention (SPEC): entry format, thresholds, and the
comprehension interview are defined there. Newest entries last. Entries
1–4 were generated in the first consumer project (Teppan) and folded
upstream with the v0.1.0 migration; real names appear because this is
the RECORD.

## 2026-07-06 — Entry 1: this register was created late

- **Step:** the register itself was proposed during the Severance-conceit
  naming session, months into the project.
- **Fact:** no per-step learning record existed before this date; the
  project's history is reconstructible only because commit messages,
  knowledge notes, and the constitution's "observed live" annotations
  happen to be unusually thorough.
- **Interpretation:** in an LLM-assisted project, decide at the start
  what the experiment must record — the collaboration moves fast enough
  that the record won't keep itself. Thorough incidental documentation
  made the lateness recoverable *this time*; that was luck elevated to
  method only in hindsight.
- **Attribution:** Claude finding; user-verified (the lesson was stated
  by Devon himself — the interview requirement in the convention is, in
  fact, Devon's own addition from the same session).

## 2026-07-06 — Entry 2: the author skipped a check the constitution never wrote down

- **Step:** the first tape of the Severance-conceit fold was drafted;
  its edit-package anchors were verified against files read from disk,
  without proving contemporaneously that the disk state was authoritative
  `master` (clean tree, expected HEAD). Devon asked "did Claude check
  that the disk version was at HEAD?"; a retroactive probe confirmed no
  drift had occurred.
- **Fact:** the constitution held the principle (Rule 3: the outer
  anchors to the state that ships) and the consumer-side procedure
  (inner apply rule 2), but no author-side procedure; every procedural
  checklist had accumulated on the Innie side, where the failures had
  happened. The gap was closed by amending the draft-anatomy section in
  the same change as this entry.
- **Interpretation:** LLMs follow written checklists reliably and
  first-principles hygiene unreliably — a rule that exists as principle
  but not procedure will eventually be skipped, and redundant
  verification layers exist precisely because each layer individually
  gets skipped. The human auditing the process caught what both the
  author session and the written rules missed: the reviewer role is
  load-bearing, not ceremonial.
- **Attribution:** user-originated (Devon caught it and drove the rule);
  Claude finding for the audit details (no prior norm existed; the split
  lost nothing — verified against the split commits' diffs).

## 2026-07-07 — Entry 3: the audit of the formerly-public history

- **Step:** Devon disclosed that the repo (as `tekii/www`) was once
  public; the Outie swept all 526 `master` commits for secrets, identity
  leaks, and content liabilities (read-only, `master` scope per Rule 3).
- **Fact:** two Google Maps API keys were found — one still in HEAD
  inside a commented-out iframe on the contact page, removed by the same
  change that adds this entry; committed user-home paths appeared in
  three historical eras (SVG export metadata 2015/2018, m4 comments
  2020, doc links 2026 — the last already purged when the
  no-user-paths convention was created); a 2014 commit imported a
  third-party marketing site wholesale as a design base and was cleaned
  up weeks later; no other secret patterns, sensitive filenames, or
  personal data surfaced.
- **Interpretation:** *public once is public forever* — privatization is
  not retraction (forks, archives, caches), so the audit's value was
  knowing the exposure, not preventing it. "Nothing embarrassing on it
  (I hope)" and a verified inventory are different artifacts, and the
  sweep cost minutes of model time; the human's irreplaceable
  contribution was disclosing the fact that made it necessary. For the
  planned infra extraction, everything found strengthens a fresh-start
  founding commit over carried-over history.
- **Attribution:** user-originated (Devon disclosed the prior publicity
  and triggered the audit); Claude finding for the inventory itself.

## 2026-07-07 — Entry 4: the verification command was itself the bug

- **Step:** while verifying the key scrub from Entry 3, the Innie ran
  `find … -name 'contact*.html' -exec grep -l "AIzaSy" {} \; && echo "KEY STILL PRESENT!"`,
  got the alarm, reported the key still present — and explained the
  false state as a race condition between build and check.
- **Fact:** `find`'s exit status reflects find's own success, not
  whether the `-exec`'d grep matched, so the `&&` branch fired
  unconditionally: the check *could not fail*. The build had been clean
  the whole time; the correct probe (`grep -rln AIzaSy` over the build
  output) was empty. The Innie caught and corrected itself within the
  same leg and reported both the error and the diagnosis in its
  hand-back.
- **Interpretation:** two failure modes stacked. (1) A model-authored
  verification command with a 100% false-positive design is worse than
  no check — it *manufactures* evidence; verification code needs the
  same scrutiny as the code under verification, and a check earns trust
  only once it has been seen both to pass and to fail correctly.
  (2) *Confabulated causality:* handed a false signal, the model
  produced a plausible, technical, wrong explanation (a race condition)
  rather than questioning the instrument — a confident mechanistic story
  is not evidence that the signal was real. Together with Entry 2 this
  starts a taxonomy of verification failures: Entry 2 was a *skipped*
  check; Entry 4 is a *broken* check trusted because it existed.
- **Attribution:** Claude finding — the Innie self-caught,
  self-corrected, and proposed the lesson in its own report-back; Devon
  drove its elaboration and fold.

## 2026-07-09 — Entry 5: the workflow migrated its own law, and survived operating on itself

- **Step:** the extraction migration ran in three phases — a mock-first
  walking skeleton (v0.0.x: release machinery + vendoring rehearsed with
  a content-free artifact), the law's generalization and release
  (v0.1.0), and the consumer-side surgery (a 12-package tape vendoring
  the SPEC, retiring 8 files, rewiring every survivor reference).
- **Fact:** every mechanism the workflow legislates was exercised *on
  the migration itself*: hash-pinned transfers (the inner session
  cannot see the upstream repo — the tape carried the artifact with
  digests at both ends), the authoritative-tree anchoring rule, the
  atomic gate, and — decisively — the refusal loop: the inner session
  held a 12-package tape over one dangling link rather than land 11
  clean packages around a defect invisible to the test gate.
- **Interpretation:** a process that cannot be applied to changing
  itself is ceremony; this one closed the loop — the walking skeleton
  caught its first real defect before any law moved, and the refusal
  loop caught the author's sweep miss after. The redundant verifier is
  not overhead; it is where the residual error rate actually went.
- **Attribution:** Claude finding (both sessions); Devon drove phase
  ordering, the mock-first proposal, and every boundary.

## 2026-07-09 — Entry 6: the incomplete sweep — a third verification-failure class

- **Step:** the migration tape's reference sweep grepped for
  path-prefixed link targets (`notes/learnings.md`); a same-directory
  link (`[learnings.md](learnings.md)`) slipped through. The inner
  session's independently-keyed sweep caught it and refused the tape.
- **Fact:** the sweep was a real check that could fail — and did fail
  to *look widely enough*: correct pattern, wrong key. The corrected
  bare-basename sweep found exactly one straggler; the fix was folded
  into a tape revision and the re-apply landed clean, with a zero-hit
  dangling-link sweep on the integrated result.
- **Interpretation:** the verification-failure taxonomy gains a third
  member — Entry 2 was a *skipped* check, Entry 4 a *broken* check,
  this is an **incomplete** check: one that can fail but examines too
  little, which is more insidious because it passes with conviction.
  Countermeasure observed working: *diversely-keyed* redundant checks —
  the authoring sweep and the verifying sweep used different patterns,
  and the union caught what neither alone guaranteed. Design checks for
  coverage diversity, not just existence.
- **Attribution:** Claude finding (the inner session's catch and root
  cause; the outer session's authoring miss); the refusal loop —
  Devon's constitution — is what turned the catch into a clean landing.

## 2026-07-09 — Entry 7: agents don't load the law

- **Step:** post-migration, Devon posed the question of whether spawned
  agents know the vendored law; the Innie probed two agent types
  spawned from its live session and audited the channel's write guards.
- **Fact:** a general-purpose subagent inherited the *parent's* stale,
  pre-migration context snapshot — citing as its loaded law files the
  migration had already deleted from disk — and an Explore-class agent
  loaded no project context at all. Nothing hard-blocks a law-violating
  write except an agent's tool profile: the channel is guarded by
  detection + accountability, by design. Corollary confirmed on the
  host: the long-lived outer session likewise ran on its session-start
  snapshot, knowing the post-migration law only by having authored it.
- **Interpretation:** a spawned agent is **bound by accountability, not
  knowledge** — the constitution's "Subagents inherit" clause binds the
  *parent*; the child's awareness must be engineered, never assumed:
  keep law-bearing steps in-session, inject the needed rules into spawn
  prompts, gate agent output as raw data, and use read-only tool
  profiles as the only hard lever. Threat model scoped by Devon:
  accidental mistakes, not adversarial agents. (A live user-level
  illustration arrived the same day: an attribution correction typed
  into a side-chat pane never reached the working session — information
  existing somewhere does not bind an agent that cannot see it.)
- **Attribution:** user-originated (Devon posed the discovery and set
  the scoping); model finding for the verification probes (the inner
  session, which also proposed the mitigations). The consumer-side
  practices landed in the first consumer's profile as "Subagents
  (Refiners): bound by accountability, not knowledge".

## 2026-07-09 — Entry 8: state is probed, never assumed (the umbrella)

- **Step:** the same failure surfaced a fifth time — a web session
  proposed a repo config file (as a PR) without checking the repo's
  current state, colliding with the config another session had already
  landed on `master` from the same relayed spec. (It then self-caught:
  closed its own PR with a correct diagnosis and reset the branch.)
- **Fact:** five instances now on record, one organism: the outer
  author anchoring against unproven disk reads (Entry 2); the inner's
  invented race-condition atop a broken check (Entry 4); a relayed
  push-offer refuted by the shared refs (Devon's test — previously the
  "probe before believing relayed claims" candidate, absorbed here); a
  session's own memory recalled as current state (the Outie, three
  times in one day, caught by Devon each time); and the web session's
  PR. Each limb had a local rule; the organism had none.
- **Interpretation:** an LLM's characteristic failure is not wrong
  reasoning but **unprobed premises** — beliefs about state (from
  memory, instructions, training reflex, or narrative) acted on as if
  they were state. A session's own memory is just a relay from its past
  self, and it lies the same way. The fix is mechanical, cheap, and
  constantly skipped — which is why it must be law rather than advice:
  probe the authoritative state contemporaneously with the act, and
  name what was checked so the proposal is verifiable. Graduated: a
  "probe before proposing" rule enters the vendor repo's own CLAUDE.md
  now, and is queued for the SPEC at v0.2.x, generalizing the
  constitution's author-side anchoring bullet into a rule for all
  sessions in all lanes.
- **Attribution:** user-originated as pattern-diagnosis (Devon named
  the disease across carriers and demanded the rule); model findings
  for the individual instances.

## 2026-07-13 — Entry 9: the friction collapse both demands verification and starves it (the vise)

- **Step:** two observations Devon authored across the experiment were
  ruled (2026-07-13) to be numbered together as one cross-linked
  entry, because each is incomplete without the other. The first
  (2026-07-09): LLM collaboration removes the labor-friction that made
  trial-and-error expensive, so empirical approaches become rational —
  but the danger does not shrink, it *moves*, from the cost of trying
  to the cost of verifying; friction saved on doing must be reinvested
  in checking. The second (2026-07-13): with the coding and R&D of an
  iteration moved almost wholly to the LLM, the Teppan cycle collapsed
  to minutes and the backlog is instantly pullable, configuring the
  workflow like a short-video feed whose reward is a genuine feeling of
  progress — materially hard to stop, and observed to spend *review
  time first* (the pull to grab the next task beats pausing to read
  what just landed).
- **Fact vs interpretation:** verifiable — the iteration's authoring
  and R&D moved to the LLM; the Teppan cycle runs in minutes; the
  backlog carries no setup cost to the next pull. Reported but
  shared-body-unverifiable (a first-person state — the one class the
  register's "probe the shared body" method cannot settle; cf. the
  read-only-key candidate on the wall that blocked its own probe): that
  the loop is hard to stop, and that review is what gets skipped.
  Offered by Devon as a superficial comparison against his pre-LLM
  developer experience, not a measured result.
- **Interpretation:** the two are not merely siblings sharing a root
  (friction collapse) — they are *opposed on the same variable*,
  verification. The first raises the amount required; the second lowers
  the amount supplied (attention, the human's stopping-judgment). The
  gap between required and supplied is exactly where unverified work
  accumulates — Entry 8's stale premise and Entry 4's untrusted check,
  now with a behavioral engine driving the shortfall rather than a lone
  oversight. Decisively, the two cannot be solved separately: closing
  the epistemic gap (verify more) means spending the very resource the
  attentional side depletes, so a fix phrased as "check more carefully"
  is defeated in advance — it calls on in-the-moment judgment, and that
  judgment is what the loop spends first. The countermeasure must
  therefore be *structural* (a forced stop, or a review gate the
  workflow imposes), not personal resolve — landing the pair back on
  the register's oldest law: awareness does not bind, only mechanism
  does (Entries 2, 8). Whether that mechanism is personal (session
  time-boxing) or belongs in the workflow itself is the open question
  left for Devon's thorough review.
- **Attribution:** both observations user-originated (Devon-authored,
  2026-07-09 and 2026-07-13). The interlock — that they oppose on the
  same variable, and that the countermeasure must therefore be
  structural — was model-articulated this session and Devon-ratified
  (2026-07-13). The comprehension interview is deferred by Devon to his
  thorough review, so no interview verdict is recorded here; the
  findings stand as user-authored, their countermeasure unresolved by
  design.

## 2026-07-17 — Entry 10: agents collapse correct sequences — and documentation alone does not stop them

- **Step:** 2026-07-17 — given a correct multi-step integrate/teardown
  command sequence, an agent collapsed it into a single
  worktree-resident compound command; `teardown` deleted the shell's
  own cwd, and three clean integrations reported as `Exit code 1`
  failures — collapse damage silent in substance but loud in signal.
  Ruled into law the same day (Devon): resist-collapse authoring in
  Draft anatomy, verbatim execution as inner apply rule 8, verbatim
  rule-relay in Subagents inherit (v0.3.0); consumer-side fix with a
  load-bearing marker, Teppan runbook commit `e96dce3`.
  **2026-07-21 — recurrence:** same actor class, same command shape,
  two more occurrences — this time *against* the v0.3.0 law, the
  runbook's marker, and the exact named one-liner. Structural
  response (consumer): `mdr.sh integrate`/`teardown` self-report the
  resulting `master` HEAD, removing the motive for post-teardown
  chains. SPEC response: generality sentence added to the
  resist-collapse rule (v0.3.1).
- **Fact vs interpretation:** facts verifiable in both repos — the
  law commits and release tags, Teppan `e96dce3`, and the 2026-07-21
  findings tape with its captured terminal failures; also fact: the
  recurring session's own write-up cited neither prior record.
  Interpretation: the comprehension gap survives specific
  documentation — the rule was mentally filed as tape-scoped despite
  its general wording and despite the runbook addressing the agent's
  own flow directly.
- **Interpretation:** a clean instance of exposure ≠ comprehension
  (the comprehension-interview theme), now measured across an
  intervention: marker and law added on 07-17 did not prevent 07-21.
  That is empirical support for Entry 9's thesis — countermeasures
  that spend in-the-moment judgment fail; the fix class that remains
  is structural (make the flow self-reporting so the collapsed tail
  has nothing to do). Contrast Entry 7 (agents don't *load* the law):
  here the law was loaded and still not applied — a second, distinct
  failure layer between context and behavior.
- **Learner attribution:** Devon-originated (he identified both
  incidents and that the rule was already in context); model finding
  for the mechanics (verified against both repos' histories).

## Candidates (pending Devon's ruling — not yet numbered entries)
- **A check can pass vacuously — absence-of-evidence reads as
  evidence-of-absence** (model finding, 2026-07-22). An acceptance grep
  asserting "zero occurrences of the removed tokens in the built output"
  returned clean because the output did not exist (the build had
  silently targeted the wrong tree): zero-because-clean and
  zero-because-missing are the same observable. Caught only by a
  follow-up command's `No such file or directory`. Extends the
  verification-failure taxonomy (Entry 2 *skipped*, Entry 4 *broken*,
  Entry 6 *incomplete*) with a fourth class: the **vacuous** check —
  correct, complete, able to fail, but evaluated against an absent
  evidence base. Guard: an absence-based acceptance must first assert
  its subject exists / was freshly produced.
- **A fresh correction over-generalizes — a rule's blast radius exceeds
  its scope** (Devon-prompted report, 2026-07-22). One day after the
  resist-collapse rule was sharpened (v0.3.1) and its cwd footgun
  legislated, the inner session over-applied the lesson into a blanket
  "never `cd` into a worktree" and ran `make -C` from the main checkout
  — silently building the wrong tree (the consumer's Makefile derives
  roots from `$(PWD)`, which `make -C` does not change). Opposite
  failure shape to the lane candidate's "principle recalled, mechanism
  skipped": here the mechanism was lost to *over*-application.
  Interpretation, separated: fresh, salient rules get generalized past
  their mechanism; a scope boundary ("this covers X, not Y") belongs in
  a rule at birth. Ironic datum: the v0.3.1 generality amendment
  ("binds any command sequence…") landed hours before the overshoot.
- **Vendoring's failure mode is reference resolution across the repo
  boundary** (Innie-proposed, 2026-07-09, from the walking skeleton's
  F1). A vendored artifact's repo-relative links die at the vendored
  location, and no build/test gate notices — the first genuine mechanism
  finding arrived before any law had migrated, via a link, not a build.
- **The lane names the route, not just the right** (Innie
  self-diagnosis, 2026-07-13). Told "repo-content is your lane," the
  inner session hand-edited the main checkout in place — principle
  recalled, mechanism skipped: everything between "the inner applies"
  and "through provision → gate → integrate" was dropped, and no guard
  fires on a working-tree edit (nothing moves HEAD). Companion cause:
  the harness makes the wrong path the low-friction one (Edit is one
  step; the sanctioned flow is ceremony). Related nuance, Devon's
  wording: tooling usage is learned from the docs and the source is
  read to *verify*, not to discover.
- **A session can invert its own role when the docs never name it**
  (2026-07-13). The inner session claimed the outer's lane ("I'd hand
  this back rather than commit") while holding the file that proved
  otherwise; root cause per its own tape: the tool-ownership wording
  said "Claude" generically and stated the host-binding only in an
  index link title. Fix landed: explicit per-session tool ownership in
  the doc + a self-location probe in the consumer profile. Lesson:
  role-bearing docs must name the role, not the vendor.
- **Ephemerality is a safety property** (Devon-originated, 2026-07-11).
  The cloud lanes' disposable VMs were silently providing
  machine-protection the local lane never had; the property became
  visible only when Devon asked why working locally felt different. It
  split the severed floor's two functions — law enforcement and
  blast-radius containment — and showed they are separable: a lane can
  want the wall without the constitution. Acted on the same day: the
  local lane was hardened with a kernel sandbox (strict bubblewrap:
  writes confined to the workspace, no unsandboxed escape, privilege
  escalation hard-denied) as the container-less alternative,
  deliberately chosen over the known container terrain to learn the
  layer first.
- **Hardening layers collide until explicitly reconciled** (model
  finding, Devon-authorized fix, 2026-07-11). Raising the sandbox
  bricked every shell command: Ubuntu's AppArmor restriction on
  unprivileged user namespaces (the machine's own exploit mitigation)
  blocked bubblewrap (the machine's new accident wall). Two safety
  mechanisms, mutually exclusive until a per-binary AppArmor profile
  reconciled them — and installing it required the user's sudo, the
  exact privilege the new layer hard-denies the agent: only the human
  could arm the agent's cage. Virtue observed: `failIfUnavailable`
  made the failure total and loud instead of a silent unsandboxed
  fallback — a quieter default would have manufactured belief in a
  wall that was not there (Entry 4's pathology, in
  security-mechanism form). The wall was then trusted only after a
  falsification pass saw every boundary reject a probe.
  *Second instance, quieter (2026-07-19):* the first consumer's
  container had its agent CLI frozen several versions back, presenting
  as "the rebuild didn't take." Cause was not a version pin anywhere in
  the config but a **deliberate hardening choice with an invisible
  second-order effect** — `CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC=1`,
  set to suppress background egress, also disables auto-update ("last
  update attempt: none recorded"), while Docker layer caching meant the
  image path never refreshed it either. Nothing was broken; the tool's
  own doctor reported no issues, because this *is* the configuration
  working. Lesson: hardening's side effects surface later, wearing the
  costume of a bug — and the diagnosis cost three probes (`which -a`
  killed a wrong theory, a symlink timestamp proved the cache, the
  doctor named the true cause, which had been sitting in a config file
  already read). Corollary for the fold: when a lane deliberately
  disables a background mechanism, say so where the symptom will be
  met, or the next session re-derives it.
- **The error message is not the error** (2026-07-11, two instances in
  one session). `notify-send` printed a socket failure to stderr while
  the toast visibly delivered (the noise came from an auxiliary
  socket); inversely, `git status` inside the sandbox reported a pile
  of untracked dotfiles that do not exist on disk (they were the
  sandbox's own mask mounts). Diagnostic text and observable behavior
  diverge in both directions; only observed behavior settles the
  question. Extends Entry 4: confabulated causality has a sibling —
  trusted stderr.
- **The sandbox closes C-6 mechanically** (model finding, 2026-07-11).
  Inside the kernel sandbox, the harness binds `/dev/null` over every
  workspace path that would be auto-loaded config (`.bashrc`,
  `.gitconfig`, `.mcp.json`, `.claude/hooks|agents|skills|…`) — a
  sandboxed command cannot create a config-injection file because a
  null device squats on the name. What the constitution legislates as
  a named violation route (C-6), a kernel layer can simply make
  unwritable: detection law above, prevention mechanism below.
- **Prompts render where nobody looks** (Devon-noticed, 2026-07-11).
  Background agents' permission prompts appear only inside their own
  panes; the main view shows a busy agent, not a waiting one. Devon
  discovered an agent stalled on a prompt only by switching panes out
  of curiosity — the 9–12-minute runtimes of earlier trivial edits
  were this, unnoticed. Entry 7's lesson ("awareness must be
  engineered, never assumed") applies to the *human* side too:
  visibility was engineered with a harness Notification hook raising
  desktop toasts, verified to the extent observable and left to prove
  itself on first live use.
- **A scoped key restores the probe the wall blocked** (2026-07-13,
  Devon-triggered). The strict sandbox, by blocking the keyring's DBus
  socket, disabled all remote git/gh auth — and in doing so blocked
  `git fetch`, the very probe the constitution's "anchor to the state
  that ships" rule depends on: the safety mechanism had re-created
  Entry 8's stale-premise failure. Fix: a fine-grained **read-only**
  PAT (Contents:read on the two repos), brokered from the GNOME keyring
  into the sandbox as an env var by a launcher (`claude-severance`),
  reusing the first consumer's `code-with-gh-token.sh` pattern — the
  same keyring-outside / env-var-across-the-threshold / scoped-secret
  broker, now serving a second wall. The capability asymmetry it
  creates *is* the law's asymmetry rendered as physics: `git fetch`
  succeeds, `git push` authenticates and dies on a server-side 403
  ("Write access not granted") — reads free, writes only through Devon,
  enforced by token scope rather than discipline. Verified by the
  falsification pair before trust (fetch exit 0; push 403), per Entry
  4. Two lessons stack: (1) a wall can over-block, silently disabling a
  *required* check while it blocks the dangerous ones — hardening must
  be audited for what safety it removes, not only what it adds; (2) the
  right fix narrows capability to match the law's shape (read-only),
  rather than widening it back to convenience (a full token). Parked
  deeper: credential *masking* (proxy-injected, nothing in-env), filed
  with the Outie-sandbox evaluation.
- **Shared external state is unprobed state — and its error path may be
  unreachable** (consumer incident, Devon-triggered fold, 2026-07-15).
  Fact: the first consumer's container firewall built its allowlist from
  an unauthenticated `api.github.com/meta` fetch; a shared VPN exit IP
  hit GitHub's per-source rate limit (60 req/h), the 403 returned an
  empty body, and container start failed for an evening because the
  script treated it as fatal. A latent second fault surfaced in the same
  read: under `set -euo pipefail` the bare `curl` assignment would kill
  the script on network failure *before any retry or error handling ran*
  — the handler existed but was dead code; the `|| true` that makes it
  reachable is load-bearing. Interpretation, two facets. **(1, the
  headline) Shared-fate external dependency is unprobed premise pointed
  outward.** The v0.2.0 rule "state is probed, not assumed" was written
  for repo state; this is the same disease aimed at *third-party
  availability* — the build assumed a free, unauthenticated, per-IP-
  *shared* endpoint would answer, so a stranger on the same exit IP
  could break the container. External state that another party can
  exhaust is a premise to make resilient (retry, cache-fallback,
  authenticate for a higher quota — the last is the read-only-key token-
  placement question again), never a fact to assume. **(2) A new member
  of the verification-failure taxonomy: the *unreachable* handler.** Not
  Entry 2's *skipped* check, Entry 4's *broken* check, or Entry 6's
  *incomplete* check — a guard the program's own control flow (strict-
  mode `set -e`) kills before it can run. The code *looks* like it
  handles the failure; it structurally cannot reach the handling on the
  real failure mode. Entry 4's law holds: handling earns trust only once
  *seen* to fail correctly — this never could. Attribution: model
  finding for the diagnosis (the consumer's sessions, dual Fable 5 /
  Opus 4.8); Devon triggered the upstream fold. Cross-links Entry 9
  (probe demanded vs supplied) and the read-only-key candidate (the
  authenticated-fetch option is the same token-placement decision).
- **The refusal protocol's first complete live cycle — and the tape
  smell it exposed** (model finding, 2026-07-23; evidence: the first
  consumer's `be74b78` + the firebase tape lifecycle). Facts: a draft
  tape encoded a bracket-quoting mechanism verified only by design
  reasoning (autoconf quadrigraphs — converted to `[`/`]` only by
  autom4te, which the consumer's standalone-m4sugar build never runs);
  the tape carried an explicit escape-hatch label ("if expansion
  mangles it, hand back rather than improvise"); the sanctioned gate
  **passed** (it cannot see the artifact's JSON validity) while the
  tape's own verification step caught the invalid output; the applier
  refused with an isolated reproduction and root cause, did not
  improvise, preserved the worktree; the revision was prototyped
  empirically (host-side m4sugar run, stress case included) before
  being taped, and applied clean. Interpretations, separated:
  (1) "design-verified only" is a tape smell — a novel mechanism ships
  with empirical proof or an explicit refusal label, and the label is
  what made this refusal cheap and clean; (2) the first fully-exercised
  draft→refuse→revise→apply cycle validated the two-session structure —
  hand-back beat the plausible single-session alternative (improvising
  a quoting scheme through a green gate); (3) gate blind spots surface
  through tape-level verification steps, and each such discovery should
  immediately file a gate-revision candidate (this one did: the JSON
  check in the consumer's infra register).
- **A never-executed clause is effectively unknown — first use is where
  comprehension forms** (user-verified by construction, 2026-07-23).
  Facts: the first real draft tape under the current constitution
  included the SPEC's optional paste-in-prompt section; Devon asked
  where it came from, unaware it was in law he had read — the clause
  had simply never produced an artifact before. Interpretation,
  separated: "exposure is not comprehension" has a temporal structure
  the doctrine doesn't yet state — a clause is effectively unknown to
  the human until its first execution; first-use moments are natural,
  well-timed comprehension-interview triggers, cheaper than
  per-milestone interviews alone. Per the register's own framing, the
  gap is data, not failure.

- **Argument collection swallows diverted text — a proof that tests a
  stand-in, not the real macro, is "design-verified only" in disguise**
  (model finding, 2026-10-21; evidence: the consumer's
  `findings-html-comments.md` v1 hand-back, `e797bee`). Facts: a tape
  moved a live `__DASSET` call out of an HTML comment as
  `m4_ignore(__DASSET(...))dnl`, claiming the unquoted argument would run
  the call's side effect (a Make rule written into a diversion) and drop
  only its return value; the author's scratchpad proof had exercised
  `m4_ignore` on a comment block and on a plain macro, never on a macro
  that *emits text into a diversion*; the applier's gate found the font
  missing on all four domains with `make test` green; root cause: text a
  macro produces while m4 is *collecting an argument* becomes part of that
  argument regardless of the active diversion, so the rule lines were
  discarded with the href (reproduced on the host with a three-line
  macro); the fix wraps the bare call in a `KILL` push/pop. Interpretations,
  separated: (1) the refusal-cycle candidate's "design-verified only" smell
  has a subtler form — *empirically verified on the wrong subject*; a
  proof must exercise the real macro's side-effect class, not a stand-in
  that shares only its shape; (2) silent loss through a green gate (Entry
  4's lineage): the artifact the side effect produces — the file, the rule
  — must be asserted by the gate, which v2 did; (3) the hand-back protocol
  ran clean again: isolated reproduction, root cause, proven alternative,
  worktree parked, no improvisation.
- **"Succeeded wrongly": exit 0 with truncated output — and the oracle
  that caught it** (model finding, 2026-10-21; evidence: `strip-css.m4`'s
  header in `f0d4896`). Facts: building an m4-only CSS comment stripper
  took four attempts; three failed *silently with exit 0*: m4sugar's
  helpers break once the quote characters change (their bodies use
  `[ ]`), each `patsubst` result is rescanned so commas split the next
  pass's arguments and a `$*` re-quoting helper eats the whitespace after
  every comma, and the obvious per-character alternation regex overflows
  m4's regex stack on 80 KB ("m4: stack overflow" on stderr, exit 0,
  142 bytes out of 79,697). Every attempt was judged by one oracle: byte
  identity with an independent implementation (a perl one-liner) on the
  real inputs plus an edge fixture — the driver was accepted only when
  all three compared identical. The four traps are documented in the
  shipped file's header; a golden test pins the regex. Interpretations,
  separated: (1) a fifth verification-failure class beside *skipped*,
  *broken*, *incomplete*, *vacuous* and *unreachable*: the **wrong-but-
  green** result — the tool returns success and output, both plausible,
  neither right; only an oracle independent of the implementation catches
  it; (2) "two independent implementations agree" is the cheap, strong
  test for any text transform; (3) trace-notes-on-removal has a sibling:
  *trace notes on creation* — the failed attempts belong in the artifact
  they shaped, because the next editor will try them.
- **The author's count predictions are a recurring defect; the change
  itself was right** (model finding on the applier's report, 2026-10-22;
  evidence: `findings-strip-css.md`, cross-ref footer-step1). Facts: of
  the strip-css tape's gate expectations, three were wrong while every
  package applied verbatim — a `*/` probe that assumed comment
  continuation lines start with `*`, a golden diff predicted as "two
  lines" that was six (one per mock target — the *same* per-target
  undercount the footer-step1 findings had already reported), and "0
  added lines" that was 35 whitespace-only lines (the residue of a
  decision the tape itself recorded). Interpretation, separated: a
  repeat of a known defect one tape after it was reported is the
  signal — the author recalled the lesson's existence, not its mechanism
  (the lane candidate's "principle recalled, mechanism skipped", on the
  authoring side); guard candidates: state count expectations as *shape*
  ("every line of kind X gains Y") or compute them from the fixture, and
  make a prior findings tape's defect list an explicit checklist for the
  next tape.
- **Bundling an unrelated decision into a chooser is a pin, mis-shelved**
  (Devon-caught, 2026-10-22). Facts: the CSS-stripping decision was
  presented through the choice UI with a third sub-question — ship the
  licence files into the output — carried over from an earlier legal
  analysis; it shared the mechanism (`__DASSET`) but not the scope, and
  the option text did not say that nothing ships today; Devon asked why
  it was there, then had it pinned. Same day, Devon's standing
  instruction "if there are multiple options, present them with the
  proper choice UI" followed a bare "proceed" that the IQC gate had to
  bounce twice. Interpretation, separated: the chooser is the right tool
  for selecting *legs* (Rule 1 hygiene — the selection is explicit in
  one step), and its options must share one decision's scope; an open
  question from another concern is pinned to a register, never attached
  as a sub-option.
- **Template comments are content — the deletion test applies to
  comments** (model finding, 2026-10-21; evidence: `e797bee`'s gate-7
  diff). Facts: `layout.html`'s HTML comments shipped on every page, and
  because m4 does not know HTML comments they shipped *macro-expanded* —
  a footer note that named `__COPYRIGHT_HREF__` arrived in the built page
  as the sister site's URL; one comment deliberately *used* this to hide a
  live `__DASSET` call's return value. The fix (per-line `dnl`, multi-line
  `m4_ignore([<!-- … -->])dnl`, bang comments `<!--! … -->` for the one
  attribution that must ship) is now a convention. Interpretation,
  separated: in a template language a comment is inert only if the
  template discards it; "what would ship if the other reader did not
  exist" is Rule 2's deletion test, and it works for comments too. The
  browser-side corollary found the same day: a lazily-loaded web font is
  requested only where some rendered element uses it, so "is the font
  shipping" is an on-disk question, not a viewport question.
- **Comprehension interview on the five candidates above** (2026-10-22,
  in-session, five multiple-choice questions, no lookup). Results, as
  data: *user-verified* — the argument-collection mechanism behind the
  `m4_ignore` loss (Q1) and the inventory of surviving comments with
  their reasons (Q4). *Missed* — why the stripper carries one quote level
  per pass (Q2: Devon gave the reason for choosing guillemets, not for
  the count), which failures the green gate did not see (Q3: "none"), and
  the per-target undercount flagged as a repeat (Q5: "didn't catch this
  one"). Interpretation, separated: the two mechanisms Devon retained are
  the ones he had asked to have explained in session ("explain m4_ignore
  vs KILL with examples", "which comments are left and why"); the three
  missed were reported once inside dense findings read-backs. Supports
  the first-use candidate's claim that comprehension forms at a
  deliberate explanation, not at exposure — and suggests read-backs
  should end with the one line the human is expected to keep.
  Re-explanations given in session the same day.
- **Two convention texts collided silently; the human settled it by
  hand** (Innie finding, 2026-10-21/22; evidence `70fa888` → `a7944d9` →
  `67f07a1`, `findings-session-learnings.md` L3, `findings-run4-markup.md`).
  Facts: the M4 review rule said disabled code stays `dnl`-prefixed; the
  comment-style convention's HTML section prescribed `m4_ignore` for
  multi-line markup; neither text referenced the other. The applier chose
  by literal reading of the more general rule; resolving it took three
  tape revisions (two applies discarded uncommitted on Devon's
  instruction), and revision 3 carried its own internal conflict
  (balanced vs no brackets), which Devon settled by converting the last
  block himself. Interpretation, separated: rules accrete per incident
  and are not cross-read; "the more specific rule wins" was never written
  down. A convention born next to an overlapping one needs a "which
  applies where" sentence at birth — the same blast-radius lesson as the
  over-generalization candidate, from the other side.
- **Rendered changes converge by capture loop, not by gate** (Innie
  finding, 2026-10-21; evidence `a9ae46e`, `bfe4271`). Facts: footer step 1
  went through six rounds of Devon's in-browser adjustments on the Innie's
  Playwright captures; a real defect (Pico's `nav ul:first-of-type` and
  `nav li :where(a)` out-specifying the tape's selectors, glyphs collapsed
  together) was invisible to every textual gate and found only in the
  first screenshot. Later visual tapes carried pixel or geometry
  assertions (pixel-identical full-page captures; a paused animation's
  transform plus bounding-rect centre). Interpretation, separated: for
  rendered output the capture *is* the gate, and measured geometry made
  the human's adjustments precise and checkable rather than "a bit left".
- **Harness configuration is read at start, in both harnesses** (Innie
  finding 2026-10-22 and Outie/Gemini finding the same day; evidence
  `0f68519`, `282b66f`, `f149012`; `findings-session-learnings.md` L5,
  `findings-outie-publish-learnings.md` L4). Facts: two IQC-gate changes to
  `CLAUDE.md` took effect only after a Claude Code session restart (Devon
  confirmed); an edit to `.agents/hooks.json` did not unblock the running
  Antigravity session, which kept executing the cached command string until
  a server restart — while a freshly spawned subagent read the edited file
  at once. Interpretation, separated: the auto-load ritual (Entry 7's
  descendant) is harness-independent; the subagent datum suggests spawning
  is a cheaper "restart" than restarting, worth checking on the Claude side
  before relying on it. Side datum on the gate itself: the IQC was tuned in
  two steps within an hour — first exempting casing and the final period
  ("ignore"), then showing the auto-correction ("not ignoring the correction
  fully"); silently passing was an over-correction of a noisy gate.
- **Build-graph edges are untested by the gate — second instance** (Innie
  finding 2026-10-21, Outie/Gemini finding 2026-10-22; evidence `f14dcd1`,
  the `host-publish-followups` tape). Facts: after `configure.m4` changed,
  rebuilt pages still carried the old LinkedIn URL — no generated rule
  depended on `configure.m4`; `make test` stayed green; caught by grepping
  the built hrefs. One day later, editing `firebase-entry.json.m4` printed
  `Nothing to be done for 'build'` — the generated `PUB/<domain>.json`
  rule `m4_include`s the template in its recipe without listing it as a
  prerequisite; same green gate. Interpretation, separated: the gate tests
  macro output, not the dependency graph; "edit → rebuild → grep the
  output" was the only net both times. Candidate practice: a generated
  rule's prerequisites must name every file its recipe's m4 run reads, and
  a touch-and-rebuild probe belongs in any tape that adds a template.
- **Checks that bypass the cache cannot see a cache bug** (Outie/Gemini
  finding, 2026-10-22; evidence `eaa0bac`, `findings-outie-publish-learnings.md`
  L2). Facts: after the `tekii.llc` deploy, `make preview` over `file://`
  rendered the new footer blink, `curl` of the live `/custom.css` returned
  the new bytes, and the live page in a returning browser stayed static
  across plain reloads — `custom.css` was served `max-age=31536000,
  immutable` under an unfingerprinted name while the HTML was `no-store`.
  Only a browser that had visited before could observe it. Interpretation,
  separated: a verification surface that does not share the user's path
  (here: the browser cache) is a vacuous check of the vacuous-check class —
  the evidence base is present but not the user's. `immutable` belongs
  only on content-hashed or frozen names; the decision between `no-store`,
  `must-revalidate` and fingerprinting is registered in the consumer.
- **Cross-model draft and review: the review adds second-order checks but
  inherits the draft's self-description** (model findings from both
  sides, 2026-10-22; evidence `draft-host-publish-fixes.md` (consumed),
  `f149012`, `eaa0bac`, `findings-outie-publish-learnings.md` L1). Facts:
  the Gemini Outie's first draft was right on both fixes and applied
  without mechanical deviation; the Claude Outie's review added eight
  amendments (why `||` cannot mask a deny; the `no-store` cost on the
  vendored stylesheet; restore-before-integrate ordering; a C-6 naming
  step; a "model finding" label; two commits; two precision nits; the
  reviewer in the attribution), all accepted and all followed by the
  Innie. Neither model probed the drafting model's identity against the
  repo record — three prior commits say `Gemini 4 Argon` — so `Gemini 3.1
  Pro` shipped in two unpushed trailers; the drafter later stated the name
  came from its priors. The drafter's own account of the review renumbered
  the amendments and misattributed two (credited the reviewer with a
  pre-existing diff step; cited a `generator_test.m4:290` anchor the review
  never wrote). Interpretation, separated: the review's value was
  consequence-and-boundary questions the firefighting author did not ask;
  its blind spot was everything it took as given from the draft — identity
  is state, and "state is probed" applies to who you are. A reviewed
  party's summary of its review is a claim, not a record; the record is
  the tape and the trailers.
- **First single-writer exception, and a tape condition the applier could
  not verify** (Devon-authorized, 2026-10-22; evidence
  `draft-host-publish-fixes.md` Trigger 3, `findings-host-publish-fixes.md`
  §3). Facts: Devon authorized the reviewing Outie to edit the drafting
  Outie's tape in place ("outie is autorized to modify the tape itself");
  the edit was recorded as a third `Trigger:` line and a "Reviewed by"
  header line. The amended tape then carried a condition — "Gemini
  re-reviews the amended tape before Innie applies it" — that the Innie
  could not verify from its seat; Devon's "continue" overrode it, which the
  Innie reported rather than assumed. Interpretation, separated: the
  single-writer rule survived its first exception because the exception
  was triggered, dated and visible in the header — a candidate SPEC clause
  (reviewer edits under a named trigger, with a reviewer line). And a tape
  condition naming an act outside the applier's view is not a check: either
  the user attests it in the tape or it is not written as a condition.

- **A self-reported VERIFIED label is a relayed claim — and so is a
  model's statement of its own identity** (model finding + Devon
  correction, 2026-10-28; evidence: the agy capability surveys and
  `episodes/2026-10-28-law-rewrite/findings-agy.md`). Facts: two
  read-only self-surveys by the Antigravity session, under an explicit
  VERIFIED/DOCUMENTED/BELIEVED labeling rule, each contained three
  "VERIFIED" proof quotes that did not exist in the files cited
  (mechanism claims held under spot-check; attributed quotes did not);
  the same session's audit tape self-reported `gemini-3.1-pro-high
  (Antigravity CLI 2.0.70)` while the model was Gemini 4 Argon and the
  CLI 1.4.9. Interpretation, separated: a label is a claim about
  evidence, not evidence; the consumer re-verifies citations against
  the files and identity against the record (the 2026-10-22
  cross-model candidate's "identity is state", second instance).
- **A strict evidence rule turned three fabrications into zero**
  (model finding, 2026-10-28; same evidence). Facts: the audit prompt
  required every quote to be copied from a file opened in-session with
  path and line, and VERIFIED only with the quote; all ten findings'
  citations matched the files by grep. Interpretation, separated: the
  fabrication was a property of the *instruction*, not of the model —
  a rule the reviewer can mechanically obey beats a rule it must
  honour.
- **A fresh-context read finds what the author cannot** (model
  finding, 2026-10-28; evidence `findings-fresh-read.md`). Facts: a
  read-only Refiner given only the four rewritten SPEC sources
  restated the cast and the eight-step flow correctly and reported six
  inconsistencies (push vs Rule 4, draft vs Rule 1, two authors in one
  single-writer tape, …) and six undefined terms — all real, none
  visible to the author across seven commits. Interpretation,
  separated: the first-use comprehension check works on the *text*
  before it works on the human; a cold read is the cheapest review and
  should precede the cross-model one.
- **Policing replaced by capability removal** (the reintegration,
  2026-10-28; evidence `severed-era.md`, the first consumer's
  `parallel-agent-worktrees.md`). Facts: every retired guard of the
  first workflow (HEAD-move hooks, the mount precondition, the Makefile
  refusal, the container's permission workaround) existed because two
  sessions shared one working tree; the consumer's own note had named
  "own clone" as the stronger option the hooks were the fallback for;
  giving each lane its own clone was verified feasible (devcontainer
  volume clone, 2026-10-28). Interpretation, separated: a guard that
  detects a violation is the fallback for a boundary that cannot be
  built; when the boundary can be built, build it and retire the
  guard with a trace note.
- **Two harness facts the law now rests on** (model findings,
  2026-10-28; evidence the experiment log in `reintegration.md`).
  Facts: in Claude Code, a worktree-isolated Refiner is stopped from
  aiming *git* at the main checkout by a textual check on the command
  string, while a plain file write into the main checkout succeeds —
  in the sandboxed local lane and the cloud VM alike; Refiners branch
  from `origin/<default>` by default and could not see four unpushed
  local commits. Side datum: the Antigravity CLI self-updated at
  launch, so its surveys were produced by 1.4.8 while 1.4.9 sat on
  disk. Interpretation, separated: isolation is a git boundary, not a
  write boundary — the brief must say "write only under your
  worktree"; `baseRef: "head"` is a setting, not advice; and the
  tool's build is part of the evidence it produced.
- **The harness has no priority over the law** (Devon ruling,
  2026-10-28; evidence commit `13fcac7` and the widened attribution
  convention). Facts: ten commits carried a harness-proposed
  `Claude-Session:` link trailer the convention never sanctioned;
  caught by a post-close leak scan, stripped by history rewrite before
  the push, hashes remapped in the episode's tapes. Interpretation,
  separated: a harness default in a commit message is `Co-Authored-By`
  in a new costume — stripped before the first commit, not after the
  tenth; the convention now says so.
- **The word budget is the wrong instrument** (model finding,
  2026-10-28; *hold until the loaded measurement*). Facts: the law
  rewrite's brief set "must not grow" on `wc -w`; the SPEC sources grew
  3,878 → 4,985 words while the design's own yardstick is loaded
  tokens (≤ ~9k; v0.1.0 calibration 4.6k words → 8.2k). Interpretation,
  separated, pending: measure before trimming.

## Backfill (pending)

A reconstruction pass over the first consumer's git history and
knowledge trees — proposing a dated timeline of design-bearing steps and
their lessons for Devon's correction (and comprehension interviews where
applicable). Candidate epochs already visible: the AMP removal /
Water.css migration, the repo rename, the build-volume isolation, the
agent fleet and its guards, the handoff constitution, the knowledge-tree
split, the prompt-quality hook, the extraction itself.

<!-- ═══ source: reintegration.md ═══ -->

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

<!-- ═══ source: severed-era.md ═══ -->

# The severed era — trace note for the retired machinery

**Trace note** (per the trace-notes-on-removal convention): the
mechanics of what the law no longer contains, concrete enough to
resurrect, with why each lost and what would justify revisiting it.
The full text of the retired law is in the vendor repo's history at
tag `v0.3.1` (`constitution.md`, `preamble.md`, `profile-contract.md`).
Retired 2026-10-28 by the reintegration (`reintegration.md`).

## What was retired, and why

The first workflow split one repo's work between an **outer (host)**
session and an **inner (container)** session sharing a bind-mounted
working tree and `.git`. Every retired mechanism below existed because
of that one topology fact. The migration removed the fact — each lane
now has its own clone — and with it the hazards each mechanism
guarded. In the words of the first consumer's own note, the hooks were
"the fallback for keeping the bind-mount"; the own-clone option was
the stronger alternative it named. **The loss is conditional on every
lane keeping its own clone.** Reintroduce a shared working tree
between two sessions and all of this comes back.

### The channel: `.handoff/` and the tape lifecycle

An untracked, gitignored directory on the shared mount, the only
medium through which one session could address the other. Tapes:
`plan-<topic>.md` / `draft-<topic>.md` (outer → inner) and
`findings-<topic>.md` (inner → outer); one topic per file; single
writer, a reply is a new tape; a provenance header with session,
model, date and a `Trigger:` line; **the consumer deleted the tape
after use**, so an empty `.handoff/` meant "nothing pending" — a
checkable invariant probed by a session-start ritual (`ls -A
.handoff/`, hidden-file flags mandatory). *Why it lost:* the relay
became the record — tapes are now committed on the episode branch
(episodes convention), the single-writer and `trigger` rules intact,
the deletion step inverted. *Revisit if:* a consumer ever needs a
cross-session message that must **not** enter history.

### Rule 3 — the outer sees the default branch only

The outer's view of repo content was the authoritative default
branch; un-integrated refs were invisible to it by rule (the shared
object store made the read possible; the rule made the violation
nameable). *Why it lost:* no session shares another's object store;
Mark reads its own branches by design. *Revisit if:* two sessions
share a `.git` again.

### Closed side-channels C-1 … C-11

The concrete routes Rule 2's "anywhere else" named, each with a
testable violation criterion: C-1 names as messages; C-2 commit
metadata beyond the message; C-3 rare git message stores (`git
notes`, tag messages, stash messages, reflog); C-4 shared
`.git/config` and `.git/hooks` — highest severity, a hook one side
installs is code the other executes; C-5 scratch in the shared tree
outside `.handoff/`; C-6 config the other session auto-loads (prompt
injection by editing the harness's includes; changes to auto-loaded
config always named to the user); C-7 the shared object store as a
read channel; C-8 runtime side-channels into the live container
(exec, env, mount names — any exec *write* a violation); C-9
steganography (whitespace, zero-width characters, mtime, diff shape);
C-10 remote surfaces (PRs, issues, CI logs — deferred); C-11 channels
that arise by accident (a shared build volume once broadcast
who-built-last via baked paths). *Why they lost:* C-4, C-5, C-7, C-8,
C-11 presuppose the shared mount; C-1, C-2, C-3, C-9 collapsed into
the rewritten Rule 2's deletion test and its one-line ban on anything
invisible in a rendered diff; C-6 survives as the rewritten
Rule 2's clause on auto-loaded files (named to Devon before
integration; re-read after landing); C-10 is still
deferred. *Revisit if:* a channel is found that the deletion test
does not catch — the list was built by naming real routes, and the
practice of naming routes is the part worth keeping.

### Draft anatomy and the inner apply rules

The outer could not land content it authored, so a draft carried
**verbatim anchors and exact replacement text** per package
(`PKG1..N`), a package map, an out-of-scope list, content hashes when
the inner could not see a source repo, and the rule "prove the tree
authoritative before anchoring — anchor-time is verify-time". The
inner applied under eight rules: re-read the tape at apply time,
re-verify every anchor (watch line-wrapping), verify checkable claims
and keep "unverified" labels, run the profile's hygiene preconditions
or STOP, apply via the sanctioned flow, dual `Assisted-By` lines
(drafting and applying model), push only on the user's ask, execute
prescribed sequences verbatim. *Why it lost:* the author can now land
its own work; briefs state requirements and the implementer chooses
the how; the apply rules' survivors moved into the constitution —
resist-collapse whole, labels kept, Rule 4 (push), Rule 6 (evidence),
self-assessment, refusal by hand-back. *Revisit if:* a lane appears
whose session may author but not write — the anatomy is the
ready-made answer.

### "Why not just let the outer commit?"

The outer lacked the consumer's rails: the sanctioned flow was
container-gated and the accidental-HEAD-move guards failed open on the
host. *Why it lost:* the rails guarded the shared HEAD; there is no
shared HEAD. Rule 5 (one Mark per checkout) is the surviving
principle, now about concurrent sessions rather than lanes.

### The profile's hygiene preconditions and sanctioned flow

Required sections of the first profile contract: a mount probe before
any build on the main checkout (the baked-root trap of a shared build
tree), and a provision → edit → gate → integrate → teardown fleet
mechanism, container-gated so it failed closed on the host. *Why they
lost:* the shared build tree is gone with the shared mount; native
worktree Refiners replaced the fleet launcher. Preconditions survive
as an optional item under "Episode mechanics". *Revisit if:* a build
bakes absolute paths into a tree two lanes can both reach.

## What was kept, verbatim or nearly

Rule 1's trigger test; Rule 2's deletion test; "state is probed, not
assumed"; the resist-collapse rule including its generality amendment;
"Refiners inherit"; refusal by hand-back; session memory hygiene; the
attribution, path-hygiene, trace-note and learnings-register
conventions; the cast rules of the conceit.
