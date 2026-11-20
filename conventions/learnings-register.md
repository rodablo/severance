# Learnings register — record what each step taught

This workflow is an experiment (see the RECORD), and an experiment that
doesn't record its results isn't one. The **learnings register** (in the
RECORD, `learnings.md` upstream) holds what each step taught, for two
audiences: Devon, and the eventual public write-up.

This convention is the forward-looking sibling of trace-notes-on-removal:
trace notes preserve the *why* of what was removed; the learnings
register preserves what each step *taught*.

## The rule

When a change lands a **design-bearing step** (same threshold as trace
notes — no entries for routine mechanical work), the session MUST ask:
*did this step teach something about working with AI agents?* If yes, it
MUST record an entry. Entries generated inside a consumer project are
**folded upstream** into the Severance RECORD at the next interchange
Devon triggers for the purpose — law flows down in releases; experience
flows back up in folds.

## Entry format

Each entry MUST include:

- **Date + step** — what was attempted, with evidence pointers (commits,
  knowledge notes, incidents).
- **Fact vs interpretation, separated** — what verifiably happened vs
  what it suggests. The write-up's credibility depends on this line
  staying sharp.
- **Learner attribution** — a lesson MUST be marked as a *model finding*
  (verified against code/history) or *user-verified* (see below);
  sessions MUST NOT silently assume both.

## The comprehension interview

Devon reads every finding, but **exposure is not comprehension** — an
experiment about learning to code with AI agents must test what its
human actually learned. So, on Devon's trigger (per milestone, or on
demand):

- The session conducts a **short interview** — 3–5 questions derived
  from the step's lessons, answered without looking things up.
- The entry's lesson MUST be marked **user-verified** only after the
  interview confirms it. Partial or missed answers are **data, not
  failure** — they MUST be recorded (that gap is a result of the
  experiment) and trigger a re-explanation.
- The interview happens in-session between Devon and one agent; it is
  not an interchange and involves no cross-session traffic.

## Why

Publication-grade honesty: "the human read the reports" is not a
finding; "the human could answer these questions afterward" is. And
repo-visibility (per the constitution's session-memory-hygiene rules):
lessons live in tracked files, where every session and Devon can see
them — never only in a session's private memory.
