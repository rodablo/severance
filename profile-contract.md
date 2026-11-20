# The profile contract

Every consumer project MUST provide a **`profile.md`** vendored beside
this SPEC, answering the questions this law deliberately leaves open.
An adoption without a complete profile is visibly incomplete. REQUIRED
sections:

## Gate

The command(s) every integration MUST pass, with explicit pass
criteria (e.g. Cold Harbor: `make test` — every assertion PASS, 0
FAIL). Mark MUST run it on the exact merge candidate; nothing merges
without it.

## Lanes

One entry per lane the project is worked on from. Each entry MUST name:

- **the boundary** — what stops a session mechanically (a cloud VM, a
  container with its own clone, a per-command sandbox on a host);
- **the reach** — what only this lane can do (credentials, a browser,
  publishing, another model);
- **how Rule 4 is enforced** there (a harness rule that prompts
  before push, a sandbox approval, the law alone, a forwarded
  credential that must not be used without the ask);
- **the harness profile** — the file the harness auto-loads this law
  from (`CLAUDE.md`, `AGENTS.md`, …), its hook file, and any sandbox
  grants the lane needs; plus the setting that branches Refiners from
  the local HEAD where the lane works on a local checkout.

Lanes are declaration-only: profiles MUST name them by their technical
kind.

## Episode mechanics

Where briefs land (the `episodes/` root is fixed by the convention;
say what else the project expects in a brief — e.g. the acceptance
checks it must list); in which lane and how the gate is run on the
merge candidate (and which lanes cannot run it, lacking a toolchain
or a browser); which lane integrates and how (plain merge on the main
branch, or a plain-lane commit that closes the episode); any
project-specific preconditions a session must probe before building
on the main checkout, each with its failure action (STOP and hand
back).

## Reviewer

Who reviews — a read-only Refiner, a second session, another model —
and how read-only is enforced for it (tool profile, plan mode, a deny
rule). If the reviewer cannot commit, say how its findings reach the
branch (it writes the file or returns its text; Mark commits, both
attributed). The section MUST also say when a brief calls for a
cross-model review instead of the default (e.g. changes to
conventions or the gate, a trace-note removal, Devon's call at plan
approval): a same-model reviewer shares Mark's blind spots.

## Implementation docs

Where the consumer's own machinery documentation lives (container
setup, environment notes, harness configuration). This law never links
consumer files; the profile is the indirection point.
