---
type: Findings
title: Retroactive review of the v1.1.0 keyword pass
description: A fresh-context, read-only reviewer compares the SPEC sources at v1.0.1 and v1.1.0 sentence by sentence and tests the release's claim that the BCP 14 conversion preserved exact semantics; its report, and Mark's verification of each finding against the two tags.
timestamp: 2026-11-20
session: sandboxed local lane, Claude Code — a read-only Refiner spawned by Mark, given the two tags, the list of SPEC sources and the release commit's claim
model: claude-fable-5-2 (inherited)
trigger: "\"go with option 3\" (Devon, 2026-11-20) — option 3 as Mark had put it: \"A fresh-context, read-only reviewer compares v1.0.1 to v1.1.0 sentence by sentence and classifies each keyword choice as preserved, hardened, softened or new obligation.\""
branch: master
reviewer: a read-only Refiner (fresh context; cross-model to the release's author)
---

*Mark's note: this tape is retroactive. Release v1.1.0 (2026-11-19) was
authored by a Gemini session and shipped with no brief, no findings and
no independent review; this directory therefore holds no `brief.md`,
and the standard the reviewer tested is the release commit's own claim
("preserving exact semantics"). The reviewer returned this tape's text;
Mark wrote it to the file (episodes convention). The reviewer was not
given Mark's own earlier audit of the same release, and was told not to
read `NOTES.md`, `learnings.md` or anything after the v1.1.0 tag; its
own statement of what it nevertheless saw is under "Not checked /
uncertain". The text is verbatim; Mark's verification follows it.*

# Findings: review of release v1.1.0 against v1.0.1 (BCP 14 keyword pass + epistemic-voice convention)

## Verdict

**Fail** against the claim "preserving exact semantics": of 111 changed or new normative units examined, 86 PRESERVED, 10 SOFTENED, 2 HARDENED, 8 NEW OBLIGATION (7 of them the new convention itself, which the message discloses), 0 DROPPED as a separate class, 3 OTHER CONTENT CHANGE, plus 2 new declarative keyword clauses.

Three of the changes touch rules whose own stated rationale is a safety or data-loss concern (F1 to F3). The rest of the conversion is faithful.

## Coverage table

Unit = one changed sentence, or one clause where a sentence carries two independently changed rules. Every hunk of `git diff v1.0.1 v1.1.0` for each file was walked; nothing was sampled.

| File | Units | PRESERVED | SOFTENED | HARDENED | NEW OBLIGATION | DROPPED | OTHER | New declarative |
|---|---|---|---|---|---|---|---|---|
| preamble.md | 6 | 3 | 0 | 1 | 0 | 0 | 1 | 1 |
| constitution.md | 38 | 33 | 4 | 0 | 0 | 0 | 1 | 0 |
| conventions/episodes.md | 25 | 19 | 5 | 0 | 0 | 0 | 1 | 0 |
| conventions/git-commit-attribution.md | 3 | 3 | 0 | 0 | 0 | 0 | 0 | 0 |
| conventions/no-user-specific-paths.md | 5 | 5 | 0 | 0 | 0 | 0 | 0 | 0 |
| conventions/trace-notes-on-removal.md | 4 | 3 | 1 | 0 | 0 | 0 | 0 | 0 |
| conventions/learnings-register.md | 6 | 5 | 0 | 1 | 0 | 0 | 0 | 0 |
| conventions/epistemic-voice.md (new file) | 7 | 0 | 0 | 0 | 7 | 0 | 0 | 0 |
| profile-contract.md | 5 | 5 | 0 | 0 | 0 | 0 | 0 | 0 |
| CLAUDE.md (root) | 12 | 10 | 0 | 0 | 1 | 0 | 0 | 1 |
| **Total** | **111** | **86** | **10** | **2** | **8** | **0** | **3** | **2** |

All files were fully covered. Quotes below are verbatim except that source line breaks are reflowed.

## Findings

### F1. Worktree write restriction in briefs: flat rule became SHOULD, in both files (SOFTENED, blocking)

- constitution.md, "Refiners inherit"
  - v1.0.1: `A brief says "write only under your worktree"; a consumer may enforce it with a pre-tool hook.`
  - v1.1.0: `Briefs for worktree Refiners SHOULD state "write only under your worktree"; a consumer MAY enforce it with a pre-tool hook.`
- conventions/episodes.md, "Harness settings the convention depends on"
  - v1.0.1: `Briefs say "write only under your worktree"; a consumer may mechanize that with a pre-tool hook.`
  - v1.1.0: `Briefs for worktree Refiners SHOULD say "write only under your worktree"; a consumer MAY mechanize that with a pre-tool hook.`

Fact: an unqualified indicative became SHOULD, and the scope phrase "for worktree Refiners" was added in both places.

Interpretation: a brief author may now omit the statement for a reason it judges valid. The surrounding text, unchanged, says worktree isolation "does not stop a file write there", so the brief sentence is the only non-optional guard the law provides (the hook is MAY). This is a SHOULD whose rationale is a safety invariant; it also sits beside Rule 7's MUST against writes into the shared tree.

### F2. Narrowest tool profile for Refiners: imperative became SHOULD (SOFTENED, blocking)

- constitution.md, "Refiners inherit"
  - v1.0.1: `Give a Refiner the narrowest tool profile its job needs: a read-only profile is the one hard lever a spawner has.`
  - v1.1.0: `A spawner SHOULD give each Refiner the narrowest tool profile its job needs: a read-only profile is the one hard lever a spawner has.`

Interpretation: a spawner may now give a Refiner a wider profile than the job needs and remain compliant by citing a reason. The retained rationale ("the one hard lever") and the unchanged "Lanes" text (`tool profiles and deny-rules are the guards`) describe this as a guard, not a default.

### F3. "Ask Devon for the push" turned from a prompt to act into a restatement of a prohibition (OTHER CONTENT CHANGE, blocking; plus SOFTENED, should-fix)

- conventions/episodes.md, "Interrupted episodes"
  - v1.0.1: `On ephemeral lanes uncommitted work dies with the lane — commit early, and ask Devon for the push (Rule 4).`
  - v1.1.0: `On ephemeral lanes uncommitted work dies with the lane — sessions SHOULD commit early, and MUST ask Devon before pushing (Rule 4).`

Fact: "ask Devon for the push" became "MUST ask Devon before pushing", and "commit early" became "SHOULD commit early".

Interpretation: the old sentence reads as a positive instruction on an ephemeral lane to request the push so the work survives. The new one only forbids pushing unasked, which Rule 4 already does. A session may now commit, never raise the push with Devon, and be compliant while the work dies with the lane. The alternative reading, that the old text was also only a Rule 4 reminder, is possible; a reader should re-check this call. Separately, "commit early" is now waivable (Rule 8 still requires a commit before the session ends).

### F4. Refiner base ref setting: flat rule became SHOULD (SOFTENED, should-fix)

- conventions/episodes.md, "Harness settings the convention depends on"
  - v1.0.1: `Consumers worked on from a local checkout set Claude Code's `worktree.baseRef: "head"` in project settings, or push before spawning.`
  - v1.1.0: `Consumers worked on from a local checkout SHOULD set Claude Code's `worktree.baseRef: "head"` in project settings, or push before spawning.`

Interpretation: a consumer may now do neither. The same bullet records a verified failure (a Refiner that "could not see" unpushed commits). It is also inconsistent at v1.1.0: preamble.md "Adoption, in brief" step 4 keeps the unqualified imperative, and profile-contract.md "Lanes" says each entry MUST name "the setting that branches Refiners from the local HEAD".

### F5. Episodes directory not loaded by default: "is not" became SHOULD NOT (SOFTENED, should-fix)

- conventions/episodes.md, "Where episodes live"
  - v1.0.1: `The directory has its own `index.md` (draft, then pending, then merged) and is **not** loaded into sessions by default — it is consulted on demand ("why did X change?") and at session start, to list the pending episodes.`
  - v1.1.0: `The directory MUST have its own `index.md` (draft, then pending, then merged) and SHOULD NOT be loaded into sessions by default — it is consulted on demand ("why did X change?") and at session start, to list the pending episodes.`

Interpretation: a consumer may now auto-load the whole episodes directory into every session with a stated reason. "By default" already allowed on-demand reads, so SHOULD NOT adds a second escape.

### F6. Collapse-robust form: conditioned imperative became SHOULD, with a narrower actor (SOFTENED, should-fix)

- constitution.md, "Briefs resist collapse"
  - v1.0.1: `Mark such a step at the point of use ("load-bearing — do not collapse") and name the concrete failure the ordering prevents; where feasible, prefer a form that stays correct under collapse (cwd-robust, idempotent) over relying on the marker.`
  - v1.1.0: `Such a step MUST be marked at the point of use ("load-bearing — do not collapse") with the concrete failure the ordering prevents; where feasible, authors SHOULD prefer a form that stays correct under collapse (cwd-robust, idempotent) over relying on the marker.`

Interpretation: the marking half is preserved. The preference half was already bounded by "where feasible"; SHOULD lets a session skip it even when feasible. "authors" is narrower than the next sentence's scope (`any command sequence a session emits`).

### F7. Reviewer that cannot commit: obligatory either/or became MAY (SOFTENED, nit; two places)

- constitution.md, "The reviewer"
  - v1.0.1: `A reviewer that cannot commit writes the file, or returns its text for Mark to write, and Mark commits it, both named in the attribution.`
  - v1.1.0: `A reviewer that cannot commit MAY write the file or return its text for Mark to write, and Mark MUST commit it, both named in the attribution.`
- conventions/episodes.md, "Findings"
  - v1.0.1: `When the reviewer cannot commit (a read-only session, another harness, another model), it writes the file or returns the tape's text for Mark to write, and Mark commits it with both named in the attribution trailers.`
  - v1.1.0: `(when the reviewer cannot commit — a read-only session, another harness, another model — it MAY write the file or return the tape's text for Mark to write, and Mark MUST commit it with both named in the attribution trailers)`

Interpretation: read alone, the reviewer may now do neither. The neighbouring MUSTs (findings committed on the branch; each author writes its own tape) limit the practical effect. "both named in the attribution" carries no keyword in either file.

### F8. Extend an existing trace note: imperative became SHOULD (SOFTENED, nit)

- conventions/trace-notes-on-removal.md, "What the note must capture"
  - v1.0.1: `An update to an existing note is fine — when a removal completes or extends a story an existing note already tells, extend that note rather than creating a near-duplicate file.`
  - v1.1.0: `Updating an existing note MAY satisfy this rule — when a removal completes or extends a story an existing note already tells, the author SHOULD extend that note rather than creating a near-duplicate file.`

Interpretation: a near-duplicate note is now permissible with a reason.

### F9. Generated-artifact edit ban: actor narrowed (OTHER CONTENT CHANGE, should-fix)

- preamble.md, opening
  - v1.0.1: `This artifact is generated — do not edit it; edit the sources in the Severance repo and re-release.`
  - v1.1.0: `This artifact is generated — consumers MUST NOT hand-edit it; edit the sources in the Severance repo and re-release.`

Interpretation: the old imperative addressed any reader. The new one binds "consumers" and only "hand" edits, so a session, or a scripted edit, is not literally covered.

### F10. Generic example names: description became a prohibition (HARDENED, nit)

- preamble.md, "The cast"
  - v1.0.1: `(doc-only terms; they never name a real filesystem path)`
  - v1.1.0: `(doc-only terms; they MUST NOT name a real filesystem path)`

Interpretation: a statement about what the example names denote is now a binding prohibition with no stated actor. It also runs against the new convention's own text (`cast descriptions, and examples stay in natural prose`).

### F11. Learnings entry format: list gained an explicit MUST (HARDENED, nit; judgment call)

- conventions/learnings-register.md, "Entry format"
  - v1.0.1: the section heading is followed directly by the three bullets, with no lead-in sentence.
  - v1.1.0: `Each entry MUST include:`

Interpretation: an entry missing, say, evidence pointers is now a definite violation. This could equally be classed PRESERVED, since a format section is prescriptive by nature.

### F12. Refuse-by-handing-back: actor added (OTHER CONTENT CHANGE, nit)

- constitution.md, "Refuse by handing back, never silently"
  - v1.0.1: `**do not apply the bad part** and **do not silently comply or silently deviate**: write findings stating what is verified vs wrong, with the corrected mechanism, and stop.`
  - v1.1.0: `the implementer **MUST NOT apply the bad part** and **MUST NOT silently comply or silently deviate**: it MUST write findings stating what is verified vs wrong, with the corrected mechanism, and stop.`

Interpretation: the force is the same, but an unaddressed imperative now names only "the implementer". A reviewer or integrator who meets a failed precondition is no longer literally addressed.

### F13. Root session rules now self-apply the new convention (NEW OBLIGATION, nit; partly disclosed)

- CLAUDE.md, "The law here is cargo, not law"
  - v1.0.1: `Rules this repo **does** self-apply: attribution and path hygiene (above), the learnings-register discipline (the register lives here), …`
  - v1.1.0: `Rules this repo **does** self-apply: attribution and path hygiene (above), epistemic voice by document type (conventions/epistemic-voice.md — restrained ALL-CAPS modals in `Convention` / agent-instruction prose, `0` unquoted ALL-CAPS RFC 2119 keywords in `Concept` / `Reference` / `Index` / `Vision` files), the learnings-register discipline …`

Interpretation: sessions in the home repo are newly bound to the keyword-count rule for those document types. The commit message covers it only as "aligns root session rules with the convention".

### F14. The new convention's seven operative statements (NEW OBLIGATION ×7, disclosed)

- conventions/epistemic-voice.md, new file. The seven are: `grammatical voice MUST match document `type``; `imperatives MUST be used sparingly`; `Authors MUST NOT harden optional or default guidance into `MUST``; `These files MUST contain `0` unquoted ALL-CAPS RFC 2119 keywords`; `Verbatim historical quotes and dated entries MUST NOT be rewritten retroactively to fit later conventions`; ``Vision` files MUST contain `0` unquoted ALL-CAPS RFC 2119 keywords`; `SHOULD avoid lowercase normative `"must"` and `"shall"``.

Interpretation: the file is announced in the commit message, so this is not hidden. It does bind consumers: a knowledge-tree note that used a capitalised keyword unquoted was compliant under v1.0.1 and is a violation after vendoring v1.1.0. Whether that fits a minor version bump was not checked (the release-policy document is out of scope).

### Internal consistency at v1.1.0 (no before/after change; all should-fix or nit)

- **Same rule, different force.** The base-ref setting is an imperative in preamble.md step 4, SHOULD in episodes.md, and a MUST-name item in profile-contract.md (see F4). The reviewer hand-off is MAY in constitution.md and episodes.md but indicative in profile-contract.md "Reviewer" (`it writes the file or returns its text; Mark commits, both attributed`).
- **SHOULD with a safety rationale.** F1 and F2, as described there.
- **Lowercase or indicative left where a rule is clearly intended**, next to converted neighbours:
  - constitution.md Rule 2: `nothing invisible in a rendered diff (…) carries meaning` and `Names describe their referent` (the covert-channel prohibition has no keyword).
  - constitution.md "Refiners inherit": `**do not assume a Refiner has this law in its context**` and `And know the boundary's shape`.
  - constitution.md "Self-assessment": `"no deviations" stated, never implied`.
  - constitution.md "The episode flow": the whole numbered list is untouched, including step 1 `(proposal only, no edits)`, which has no keyword form anywhere.
  - conventions/no-user-specific-paths.md Rule 1 bullets: `use **repo-relative** paths — never …`, `never a real login`, `Strip the path (make it relative) or delete the dead line`; Rule 2: `Worktree parents derive from it. Git hooks stay path-free by design`.
  - conventions/trace-notes-on-removal.md: `Do not demand a note for every deleted hunk`.
  - profile-contract.md: `nothing merges without it`; `a forwarded credential that must not be used without the ask`; `preconditions a session must probe`; and the "Episode mechanics", "Reviewer" and "Implementation docs" sections, which are wholly unconverted (`say how its findings reach the branch`).
  - preamble.md "Adoption, in brief": all four steps.
  - CLAUDE.md: `Run `make check``, `Name what you checked`, `strip it`, `say so in the commit message`.
- **Effect of the residue.** The preamble text says lowercase forms "retain their ordinary English meaning", so these still bind in ordinary English. The commit message's gloss, "only ALL-CAPS keywords carry normative force", is stronger than the text; a reader who adopts the gloss would treat all of the above as non-binding.
- **MUST combined with "only" reads ambiguously** (nit): `A brief MUST exist only because Devon approved a plan` (constitution.md Rule 1); `The entry's lesson MUST be marked **user-verified** only after the interview confirms it` (learnings-register.md); `a session MUST commit or tag only when the user prompts it` (CLAUDE.md). Each can be parsed as an obligation to do the thing; a MUST NOT … unless form would not.
- **Declared but unused keywords** (nit): `SHALL`, `SHALL NOT`, `RECOMMENDED`, `NOT RECOMMENDED` and `OPTIONAL` appear only in the two keyword lists and have no operative use in any in-scope file.

## Epistemic-voice convention

**What it guards against.** Its "Why" names two failures: descriptive notes that borrow `MUST` being read as law, and aspirational notes being read as instructions. The keyword-count rules for `Concept` / `Reference` / `Index` / `Vision` address both.

**What it leaves unguarded.**
- **Softening.** It forbids one direction only (`Authors MUST NOT harden optional or default guidance into `MUST``). Nothing forbids weakening a binding invariant into SHOULD or MAY, which is the failure this same commit shows ten times.
- **No test for invariant versus default.** `Binding invariants use `MUST`` and `strong overrideable defaults use `SHOULD`` give no criterion for telling them apart, so the choice in F1 to F6 cannot be judged against the convention.
- **Lowercase rules in `Convention` text.** The count rule covers capitals only, and the convention itself concedes that "lowercase normative `"must"`" exists. The claim `mechanically checkable` therefore holds for capitalised tokens only. No check was added: the Makefile is unchanged between the two tags.
- **Untyped and unlisted documents.** No default applies to a file with no `type`, an unknown `type`, or roles outside the list (readme, design notes, commit messages, code comments).
- **`Register` and tapes.** `Register` has no keyword-count rule, unlike the other non-`Convention` types. `Brief` and `Findings` are deferred to the episodes convention, which says nothing about voice.
- **False positives.** A `Reference` table with a column value such as REQUIRED or OPTIONAL, unquoted, is a violation as written.

**Internal consistency and defined terms.**
- "OKF" is never expanded in any in-scope file; it is described only by its shape (here and in episodes.md).
- The opening rule keys on frontmatter `type`, but membership is actually given by parenthetical role lists. The in-scope sources and CLAUDE.md have no frontmatter at all; only the built SPEC carries `type: Convention`.
- "restrained", "sparingly" and "causal directional compass voice" are not testable terms.
- The `Vision` rule says `0` of all keywords, then glosses it as ``0` `MUST` / `SHALL``, which is narrower.
- The `Register` bullet cites ``Fact:` vs. `Interpretation:`, per the learnings-register convention`; that convention requires `**Fact vs interpretation, separated**` but defines no such labels and no tense rule.
- The RFC 8174 line (lowercase keeps ordinary meaning) sits uneasily with the `Vision` SHOULD against lowercase "must".

**Compliance of the in-scope files at v1.1.0.**
- The "Why" sections of the three conventions that have them contain no capitalised keywords: compliant.
- Keyword mentions in the preamble paragraph and in the convention are backticked: compliant.
- `they MUST NOT name a real filesystem path` (F10) is a keyword in a description of example terms: non-compliant with the convention's own carve-out.
- "Sparingly" cannot be assessed. For scale: constitution.md goes from 0 to 47 MUST / MUST NOT, episodes.md from 0 to 27.
- Compliance of the `Reference` / `Register` files (the narrative artifact and its sources) was not checked; they are outside the permitted reading scope.

## Not mentioned in the commit message

- The ten softenings, two hardenings and three content changes above; the message says "preserving exact semantics".
- Scope phrase "for worktree Refiners" added in two files (F1).
- `The frontmatter must parse` became `The frontmatter MUST parse as valid YAML` (episodes.md); a clarifying addition, classed PRESERVED.
- CLAUDE.md's dependency rule gained `(sessions MUST NOT introduce runtime or build dependencies)`; the original imperative stays, classed PRESERVED.
- The message describes the preamble as declaring that "only ALL-CAPS keywords carry normative force"; the preamble text does not say that.
- The release commit adds no file under `episodes/`, although the tree has that directory with one earlier episode. Whether a tape was required for this change in the home repo was not determined.
- The CLAUDE.md title change visible in the tag-to-tag diff (an owner prefix removed) belongs to an earlier commit in the range, not to the release commit.

## Not checked / uncertain

- RFC 2119 and RFC 8174 were not consulted (outside the repository). From memory only, RFC 2119 §6 also says the imperatives are for limiting behaviour with potential for harm, which would bear on F1 and F2.
- Severity labels are my judgment. F3's reading of "ask Devon for the push" and F11's classification are the two calls most worth re-checking; F12 and F9 depend on how literally actors are read.
- Unit counts depend on how sentences are split; a different split shifts the PRESERVED total but not the list of non-preserved items.
- The built SPEC was not compared with its sources, and `make check` was not run.
- README, the narrative artifact and its sources, the design and notes files were not read, so their part of the commit is unreviewed.
- Accidental exposure: I read the first 12 lines (frontmatter) of the built SPEC at v1.1.0 to check for a `type` field. Nothing after v1.1.0 and no working-tree file was opened. Auto-loaded session context included the working-tree CLAUDE.md and a recent-commit line stating that a later release restored "three rules softened by the v1.1.0 keyword pass"; I did not open that commit, but a reader should know the hint was visible to me.

## Files opened

- `MANIFEST` at v1.1.0; diff v1.0.1..v1.1.0 for `MANIFEST`, `VERSION`
- `preamble.md`, `constitution.md`, `profile-contract.md`: diff v1.0.1..v1.1.0 and full text at v1.1.0
- `conventions/episodes.md`, `conventions/git-commit-attribution.md`, `conventions/no-user-specific-paths.md`, `conventions/trace-notes-on-removal.md`, `conventions/learnings-register.md`: diff v1.0.1..v1.1.0 and full text at v1.1.0
- `conventions/epistemic-voice.md`: full text at v1.1.0
- `CLAUDE.md`: diff v1.0.1..v1.1.0 and the release commit's own diff header
- `SEVERANCE.md` at v1.1.0: first 12 lines only
- Commit message and stat of the release commit; `git log --oneline v1.0.1..v1.1.0`; diff stat only for `README.md`, `RECORD.md`, `reintegration.md`, `thumbnail-diagram.svg`, `Makefile`; file names only under `episodes/` at v1.1.0
- Keyword and lowercase-modal greps over the ten in-scope files at both tags

# Mark's verification (2026-11-20)

**Method.** Mark re-read every before/after quote in F2–F4, F6 and
F8–F12 with `git show v1.0.1:<file>` and `git show v1.1.0:<file>`: all
match. F1, F5 and F7 were verified the same way earlier the same day,
when release v1.1.1 was prepared. Two items of the consistency section
were spot-checked (the preamble's adoption step 4 and the profile
contract's "local HEAD" item, both as quoted). The rest of that
section, the unit counts of the coverage table and the review of the
epistemic-voice convention were **not** re-verified line by line.

**Recall against a known set.** Before this review Mark's own audit had
found four softenings: the ones the reviewer reports as F1, F2, F5 and
F7. The reviewer was not given them and reported all four, plus eight
findings Mark's audit had missed (F3, F4, F6, F8–F12). Its disclosure
stands: it saw a commit subject saying that three softened rules had
been restored later, so it knew softenings existed, though not which.

**Verdict per finding** (Mark's; severity is the reviewer's unless
stated):

- F1 — VERIFIED. Already restored to its original force at v1.1.1 in
  both files.
- F2 — VERIFIED. Known before this review and left to stand at v1.1.1;
  the reviewer independently rates it blocking. Restored (see below).
- F3 — VERIFIED as a change of content. Mark agrees with the reviewer's
  reading: the v1.0.1 sentence tells a session on an ephemeral lane to
  raise the push with Devon; the v1.1.0 sentence only repeats Rule 4's
  prohibition. Mark would rate it should-fix. Restored.
- F4 — VERIFIED, including the three-way inconsistency of force.
  Restored.
- F5 — VERIFIED. Already restored at v1.1.1.
- F6 — VERIFIED as quoted. Mark rates it a nit: "where feasible …
  prefer" was already a preference, and the keyword chosen fits it; the
  added actor ("authors") is the only narrowing.
- F7 — VERIFIED. Already restored at v1.1.1 in both files.
- F8 — VERIFIED as quoted; nit, as the reviewer says.
- F9 — VERIFIED. The actor and the word "hand-" are both additions.
  Restored.
- F10 — VERIFIED. A description of example names became a prohibition,
  against the new convention's own carve-out. Restored.
- F11 — VERIFIED as quoted. Mark's view: no change of force — a format
  section is prescriptive by nature, as the reviewer allows.
- F12 — VERIFIED as quoted; nit.
- F13, F14 — VERIFIED as facts about the commit; disclosed by its
  message, no action proposed.

**Devon's ruling (2026-11-20) and the state of the tree.** F1, F5 and
F7 were fixed at v1.1.1. On this tape Devon ruled to restore F2, F3,
F4, F9 and F10 to their v1.0.1 force and to leave F6, F8 and F12 as
they are; F11, F13 and F14 need no change. The five edits are made in
`constitution.md`, `conventions/episodes.md` and `preamble.md` and ship
with the release that carries this tape. Of the gaps named in the
epistemic-voice convention, two were closed on Devon's ruling the same
day: the guard on force now runs both ways, and the convention gives a
test for invariant versus default (the rule's own stated reason). The
consistency section's list of unconverted rules and the convention's
other gaps were not acted on (NOTES.md, open items).
