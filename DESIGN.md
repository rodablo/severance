# SEVERANCE — preliminary packaging & migration design

**Status: PRELIMINARY.** Drafted 2026-07-07 by the outer Teppan session
(Claude, `claude-fable-5`) on Devon's instruction, distilling a design
conversation held in that session. Nothing here is final; the "Open
decisions" section is the honest list. Re-verify any claim about the
Teppan tree against `tekii/teppan@master` before acting on it.

## What this project is

**Severance** is the severed multi-session AI workflow extracted from
`tekii/teppan`'s `knowledge-infra/` tree: the handoff constitution, its
conventions, the cast (Devon = the user, Outie = outer session, Innie =
container session, Refiners = spawned agents), and the learnings of the
experiment that produced it. Teppan is the first consumer. The eventual
goal is public presentation (experiment / paper), with this repo as the
publishable artifact.

**2026-10-28 — superseded in part.** The workflow's second form,
**Unsevered**, replaced the host/container split with lanes that each
hold their own clone, and the handoff channel with episodes recorded
in the repo; the cast is now Devon, Mark and Refiners. The design
record is `reintegration.md`; the retired mechanics are traced in
`severed-era.md`. The packaging and release design below is
unchanged. Constraint 2 still holds in its plain reading: this repo is
worked on in a single-session lane with no consumer machinery — and
now that no lane has a role split, nothing about it is special.

## Constraints (facts, not preferences)

1. **Consumers must be self-sufficient from a single clone.** Cloud
   sessions (Claude Code web, Codespaces) clone one repo; no sibling
   folders, no local Severance checkout may be assumed. Any "reference"
   mechanism that points outside the consumer repo is broken there.
2. **Work on THIS repo happens mostly in Claude Code web** (Devon,
   2026-07-07): no dev container, no Innie, no outer/inner split — a
   plain single-session lane. The workflow repo does not itself run the
   severed workflow; its own contributor rules (a future `CLAUDE.md`
   here) should be written for that simpler reality.
3. **Near-zero dependencies:** GNU Make + POSIX shell only for tooling.
   (m4 was considered for the joke and declined: also a dependency, and
   markdown-vs-m4 quoting is a footgun.)
4. **Docs must work on plain-English merits** — no show knowledge
   required (anti-overstretch principle, see the conceit note in
   Teppan's `knowledge-infra/notes/severance-conceit.md` until it moves
   here).

## The three-artifact model

1. **Source tree (this repo) — the truth.** Authored as many small
   markdown files (OKF-style: file path = concept identity), e.g.
   `constitution.md`, `conventions/*.md`, `conceit.md`, `learnings.md`,
   `assets/*` (real files: `devcontainer.json`, `mdr.sh` — the fleet
   launcher, renamed from `b3-fleet.sh` on 2026-07-09, …),
   `MANIFEST`, `VERSION`, `Makefile`.
2. **Amalgamation artifacts — built, never hand-edited.**
   `make release` concatenates the tree per the MANIFEST into:
   - **`SEVERANCE.md` (SPEC)** — binding rules + the profile contract +
     bootstrap assets as extractable fenced blocks (`### FILE: <path>`),
     so adopting a project *extracts* files instead of retyping them
     from prose.
   - **`RECORD.md`** — the experiment narrative: conceit, learnings,
     history. Humans and the paper read it; consumer sessions don't load
     it.
   Split rule: *if a future consumer session must obey it → SPEC; if it
   explains how we got here → RECORD.*
3. **Consumer reference — a vendored copy, not a pointer.** The consumer
   commits the SPEC into its own tree (Teppan sketch:
   `knowledge/severance/SEVERANCE.md` + `profile.md`; exact parent dir
   still open). The copy's frontmatter (`version`, `built-from` tag,
   `date`) IS the pin; `git log` on that one file is the consumer's
   upgrade history. Next to it, `profile.md` holds the consumer's
   answers to the SPEC's extension points (gate, hygiene preconditions,
   sanctioned flow) — co-located so spec + local half read as one law.

## MANIFEST (sketch)

```
[spec]
preamble.md
constitution.md
conventions/learnings-register.md
conventions/trace-notes.md
profile-contract.md
[spec.assets]
assets/devcontainer.json
assets/mdr.sh
[record]
conceit.md
learnings.md
history.md
```

Order is meaning (the artifact reads top-down); presence is scope (an
unlisted file ships nowhere); `make check` verifies listed files exist,
asset blocks match sources, every frontmatter block in the tree would
parse as YAML (`lint-frontmatter.sh`, POSIX awk — the build quotes the
prose fields it emits, and the first consumer's previewer refused the
v1.0.0 artifact over an unquoted ": "), and the committed artifacts
equal a fresh rebuild (a check that can actually fail — see Teppan
learnings Entry 4).

## Release mechanism

- Sources are truth; artifacts are rebuilt ONLY by `make release`.
- Only release commits touch the artifacts → `git log -- SEVERANCE.md`
  is the release history, one entry per version.
- Flow: edit sources → set `VERSION` → `make release` → commit
  `release vX.Y.Z: <changelog line>` → `git tag -a vX.Y.Z`.
- The artifact's `built-from` field carries the **tag name, not a commit
  hash** (the hash cannot be known before the commit exists; tag and
  content are born together, so the tag suffices).
- Consumer update: `git show vX.Y.Z:SEVERANCE.md > <vendored path>` (or
  the raw tag URL with no clone at all) → diff → commit. Update
  triggers: binding-law changes (adopt promptly); a problem upstream
  already solved; starting any new consumer project (take latest).

## Migration from Teppan (sketch — Teppan-side steps are inner-lane there)

- **Fresh-start founding commit** here, with a pointer back:
  "Extracted from tekii/teppan@<hash>; full history remains there."
  Reasons: `knowledge-infra/` path-history is only 3 commits — the real
  history is entangled through `knowledge/`, `CLAUDE.md`, and `scripts/`
  (measured 2026-07-07); the formerly-public Teppan history contains
  audited-but-unvetted-for-republication content; the learnings
  register's backfill is a better curated history than raw commits.
  Optional: a private `filter-repo` archaeology branch, never pushed.
- **Generalization pass:** TEKii→Lumon, Teppan→Cold Harbor in prose
  (doc-only names; kebab/underscore if an identifier is ever forced);
  `TEPPAN_*` env/guard names → generic, with consumers supplying values
  via their profile.
- **Teppan-side:** remove `knowledge-infra/`, vendor the SPEC, convert
  `knowledge/conventions/handoff-integration-profile.md` into the
  co-located `profile.md`, leave trace notes + a learnings entry (the
  conventions apply to their own extraction).

## Known downsides & revisit triggers (this design is a CONDITIONAL win)

1. Two truths in one repo (tree + built artifact): drift the week
   `make check` is skipped. Mitigation: check in CI/pre-commit later.
2. The vendored pin is honor-system: a hand-edit to the consumer's copy
   creates law that exists in no upstream version. Mitigation if ever
   needed: content hash in the header + a verify step.
3. All-or-nothing adoption: one file = atomic version bumps; no
   selective clause adoption. Painful the day two consumers want
   different clauses.
4. Anchors rot: heading-anchors into a monolith break on retitling;
   the OKF tree's file-path identity is stabler (kept upstream, lost in
   the artifact).
5. Token tax compounds: the SPEC loads whole into every consumer
   session forever. Budget in **harness-measured tokens** — v0.1.0
   measured **8.2k loaded** in a real session against a 4.6k words×1.3
   estimate (markdown-heavy prose tokenizes ~×2.3/word); current
   budget: **SPEC ≤ ~9k measured** (net cost to the first consumer was
   ≈ neutral vs the includes it replaced)
   or it degrades silently. *2026-11-20:* the `[spec]` sources are
   5,700 words at v1.1.1 — ≈ 10.2k by the same ratio, over the budget
   on paper and still unmeasured in a session (NOTES.md, open items).
6. Calibrated to today's circumstances, not virtues: single author,
   prose-dominant law, whole-law adoption, few consumers. **Reopen this
   design when any of these flips:** contributor #2 arrives, selective
   adoption is wanted, the SPEC outgrows its budget, or rendered
   (HTML/PDF) releases are needed for the publication.

## Open decisions

- Parent directory of the vendored copy in consumers (`knowledge/…` vs
  infra-side placement — Teppan's split argues infra-side).
- Whether consumers vendor `RECORD.md` or only link it.
- Whether SPEC and RECORD stay two files or the SPEC further splits if
  the token budget pinches.
- The profile contract's exact required sections.
- This repo's own `CLAUDE.md` (written for the web/single-session lane,
  per constraint 2) and its license (public-repo prerequisite).
- Naming tiers for environments ("desks", "branch offices") remain
  parked in Teppan's deferred-work register.
