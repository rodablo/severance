# NOTES — working notes & open items (not shipped in any artifact)

**Status:** maintained alongside DESIGN.md; items graduate out of here
into sources (SPEC/RECORD), the MANIFEST, or decisions — and get
replaced by one-line pointers when they do.

## Graduated

- **Prior art & name collision** → folded into the RECORD as
  `prior-art.md` at v0.1.0 (de-identified per Devon: facts retained,
  the colliding project not named; re-locate it at publication time).
- **Entry 5 candidate (probe before believing relayed claims)** and the
  **friction lesson (Devon-authored)** → imported into `learnings.md`'s
  "Candidates" section at v0.1.0, pending Devon's ruling to number them.
  The Innie's **F1 vendoring lesson** joined them.

## Graduated (v0.1.1)

- **OKF-conformant artifact frontmatter** → build.sh emits
  type/title/description/tags/timestamp + version pins (SPEC
  `Convention`, RECORD `Reference`); consumers become conformant on
  re-vendoring v0.1.1 (Devon's requirement: the consumer side must be
  OKF-valid).
- **Token budget recalibrated** → DESIGN.md downside #5 now states the
  harness-measured reality (8.2k loaded at v0.1.0; budget ≤ ~9k
  measured; word×1.3 underestimates markdown ~×2.3).
- **Agents-don't-load-law register fold** → Entry 7 (user-originated;
  model finding for the probes; Devon's accidental-mistake scoping).

## Graduated (v0.2.0)

- **"Probe before proposing" as a general rule** → constitution.md new
  section "State is probed, not assumed" (register Entry 8 generalized
  to all sessions in all lanes; the author-side anchoring bullet and
  the session-memory expiry rule named as its instances).
- **Subagents-inherit awareness sentence** → constitution.md
  "Subagents inherit" now warns a spawned agent may hold none of the
  law or a stale snapshot — verify or inject, see the profile (register
  Entry 7, vendor-neutral; harness mechanics stay in consumer
  profiles).

## Graduated (next release — the reintegration, 2026-10-28)

- **No experiments in the shared working tree** → constitution.md
  Rule 7 (Devon's ruling at the law-rewrite plan).
- **Mandatory self-assessment on every tape application** →
  constitution.md "Self-assessment before hand-back" (same ruling).
- **Sandbox for the Outie** → resolved by the lane model: the bare
  host is one lane with the per-command sandbox as its boundary;
  per-lane boundaries are the profile's business (profile-contract
  "Lanes"; `reintegration.md`).
- **Who updates the vendored package in consumers** → resolved: any
  lane vendors (every lane has its own clone); no tape ceremony; Rule 4
  governs the push.

- **The auto-load ritual + the C-6 obligation** → constitution.md
  Rule 2's clause on auto-loaded files (named to Devon before
  integration; re-read after landing) — restored on the cross-model
  audit's finding F6.

## Graduated (v1.1.0)

- **Modal keywords and epistemic voice** → preamble.md (the BCP 14
  declaration), every `[spec]` source (ALL-CAPS keywords), and the new
  `conventions/epistemic-voice.md` (voice by OKF document type).
  Upstreamed from a consumer's knowledge tree by a Gemini session in
  Antigravity and landed as one release commit. Recorded as fact: no
  brief, no findings and no independent review exist for it under
  `episodes/` — the v1.0.0 law rewrite had all three.

## Graduated (v1.1.1)

- **Read-only audit of v1.1.0** (2026-11-20) → three rules the keyword
  pass had softened restored (episodes directory not loaded by default;
  "write only under your worktree" back to `MUST`; a reviewer that
  cannot commit `MUST` either write the file or return its text); the
  README's release badge made static and owner-free. The fourth
  softening (narrowest tool profile, `SHOULD`) was left to stand.

## Graduated (next release — the reviewer tier)

- **SPEC wording: "cross-model when one is available"** (raised by
  Devon, 2026-10-29) → constitution.md "The reviewer": a cross-model
  review is required only when the brief calls for it; profile-contract
  "Reviewer" has the consumer say when briefs do. Why: the old phrase
  read as "mandatory whenever another model exists", and one agy audit
  per episode costs two relays by hand plus Mark's citation check
  (Rule 6; agy fabricated quotes in two of three runs). Cost of the
  tier, stated: a same-model Refiner shares Mark's blind spots — this
  repo's first episode's one law gap (the auto-load clause, F6) was
  found by agy alone. Parked through v1.1.0 and v1.1.1.

## Graduated (next release — the v1.1.0 review)

- **v1.1.0 has no episode record** → Devon ruled for a retroactive
  review (2026-11-20). A fresh-context, read-only Refiner compared the
  SPEC sources at v1.0.1 and v1.1.0 sentence by sentence; its tape is
  `episodes/2026-11-20-keyword-pass-review/findings-fresh-read.md`
  (no brief: there was none to review against but the release's own
  claim). It reported the audit's four softenings unprompted and eight
  further changes.
- **Five more rules restored to their v1.0.1 force** (Devon's ruling on
  the tape's findings): the narrowest tool profile for a Refiner is
  `MUST` again (F2, left to stand at v1.1.1); on ephemeral lanes a
  session `MUST` commit early and ask Devon for the push — a prompt to
  act, not a restatement of Rule 4 (F3); a consumer on a local checkout
  `MUST` either set the base-ref setting or push before spawning (F4);
  the generated artifact `MUST NOT` be edited, by anyone and by any
  means (F9); the example names "never name" a real path — a
  description again, not a prohibition (F10).
- **The epistemic-voice convention guards one direction** →
  conventions/epistemic-voice.md: the guard on force now runs both
  ways (no hardening, no softening; choosing or changing a keyword is
  a law change, reviewed as one), and the keyword follows the rule's
  own stated reason — a harm makes an invariant, convenience or style
  a default. Why: the convention forbade hardening only, and ten
  softenings passed under it in the commit that introduced it; it also
  gave no test for telling an invariant from a default (the review's
  finding). By that test the five restorations hold, and F6 and F8,
  left as `SHOULD`, are defaults.

## Open items
- **SPEC size against the token budget — measure, then decide.** The
  `[spec]` sources stand at 5,753 words in the working tree (5,052 at
  v1.0.1, 5,699 at v1.1.0); by the v0.1.0 ratio (4.6k words → 8.2k
  loaded) that is ≈ 10.3k tokens against the design's ≤ ~9k. An
  estimate only: the loaded measurement asked for since 2026-10-28 is
  still pending (register candidate "the word budget is the wrong
  instrument"). DESIGN.md downside #6 names "the SPEC outgrows its
  budget" as a trigger to reopen the packaging design.
- **Residue of the v1.1.0 review, left to stand.** F6 (collapse-robust
  form: "authors `SHOULD` prefer"), F8 (extend an existing trace note:
  `SHOULD`) and F12 (refuse-by-handing-back names only "the
  implementer") were judged minor and not changed; the review's list of
  rules left in lowercase or imperative form beside converted ones was
  not acted on, nor were the convention's smaller gaps: the
  "mechanically checkable" claim has no check behind it and covers
  capitals only, "restrained" and "sparingly" are untestable, files
  with no `type` have no default voice, and `Register` has no keyword
  rule (tape:
  `episodes/2026-11-20-keyword-pass-review/findings-fresh-read.md`).
- **Register rulings — deferred by Devon (2026-10-28), with a
  consolidation proposed.** 35 candidates pend (27 in the register's
  Candidates section before 2026-10-28, 7 added that day, 1 on
  2026-11-20). Proposed
  shape, for Devon's ruling when he takes it up — seven entries:
  *Entry 11* the verification-failure taxonomy completed (vacuous,
  unreachable, wrong-but-green; the error message is not the error;
  checks that bypass the cache; untested build-graph edges; vendored
  links; comments shipped through a green gate); *Entry 12* rules
  over-reach and collide at birth (over-generalization, the lane
  names the route, role inversion, count predictions, bundled
  decisions, colliding conventions); *Entry 13* isolation as physics
  (ephemerality, hardening layers collide, the sandbox closes C-6,
  the scoped key, shared external state, harness config read at
  start, policing replaced by capability removal); *Entry 14*
  visibility engineered for the human (prompts render where nobody
  looks, capture is the gate); *Entry 15* comprehension forms at
  first use and deliberate explanation (never-executed clause, the
  interview results, the fresh-context read); *Entry 16*
  "design-verified only" and the refusal cycle; *Entry 17* the other
  model — independence is worth what you verify (cross-model review,
  the single-writer exception, VERIFIED and identity as relayed
  claims, the strict evidence rule, harness facts, the harness has no
  priority over the law). *Hold:* the word budget. Weakest merges to
  question: comments→11, bundled decisions→12, harness config→13.
  Comprehension interviews on Devon's trigger.
- **Lesson → convention graduation hierarchy** (Devon's future ask, his
  trigger): document how register entries (case-law) graduate into
  binding conventions (law); precedent: Entry 2 → the constitution's
  draft-anatomy bullet. Natural home: this repo's docs.
- **Assets deferred from the SPEC** (v0.1.x): the consumer machinery
  (container config, fleet scripts, guards) still lives, ungeneralized,
  in the first consumer's repo. Generalizing it into `[spec.assets]`
  extractable blocks is future work — likely v0.2.x.
- **"Report-back by exception"** — discussed and deliberately left
  unadopted (Devon self-tracks); silence-must-be-a-contract caveat
  recorded in the session that raised it.
- **No experiments in the shared tree** and **mandatory
  self-assessment** → graduated (block above). Their incident
  evidence — the first consumer's `driver.m4` overwrite of an
  untracked file (2026-07-23) and the two voluntary self-disclosures
  (2026-07-13, 2026-07-23) — remains the learnings-register candidate
  pair.
- **SPEC candidate: attribution beyond the dual lines — reviewers,
  non-cast participants, and Devon's reshuffle idea** (Devon's trigger,
  2026-07-24). Precedent: the first consumer's `be74b78` carries three
  trailers — `(drafting)` Fable 5, `(reviewing)` Gemini 3.5 Flash,
  `(applying)` Opus 4.8 — exceeding both the SPEC's attribution section
  (which only rules Assisted-By over Co-Authored-By) and the consumer's
  dual-line apply rule. Four questions currently answered by
  improvisation: (1) **role vocabulary** — propose an open-but-meaningful
  set of role parentheticals, one line per participant, in pipeline
  order (drafting → reviewing → applying); (2) **threshold** — a line
  for any AI participant whose contribution is visible in the artifact
  chain (tape provenance, findings, applied edits); (3)
  **cast-independence** — attribution is orthogonal to the cast (a
  reviewer that is neither Outie/Innie/Refiner still gets its line);
  the workflow rules do NOT thereby extend to non-cast participants;
  (4) **the single-writer wrinkle** — reviewer input enters via Devon
  or via the reviewer's own artifacts; a Devon-mediated edit to the
  author's provenance header is the sanctioned form (Devon's
  prerogative, not an exception to single-writer). **Devon's reshuffle
  seed (his framing, to iterate before ruling):** restructure the line
  format along the lines of `MODEL/ROLE on behalf of AUTHOR` for the
  agent making the commit — i.e. the trailer names the acting model
  *and* its role *and* whose authority it acted under, rather than
  today's flat `Assisted-By: Model (role)` lines. Open sub-questions
  for that iteration: does `on behalf of` name Devon (the human
  authority) or the drafting session (the content author)? does the
  git author/committer identity itself change, or only the trailers?
  and does the format stay `Assisted-By:`-prefixed for tool/forge
  compatibility? Natural home once ruled: the SPEC's "Git commit
  attribution" section, `be74b78` cited as precedent.
