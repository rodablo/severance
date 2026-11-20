# Epistemic voice by document type

In an OKF repository (markdown files headed by YAML frontmatter whose
`type` names the document's role), grammatical voice MUST match
document `type` so a single sentence read in isolation — in a search
hit, a review citation, or loaded context — signals its epistemic force
to humans and sessions alike:

- **`Convention`** (this SPEC, the consumer's `profile.md`, committed
  convention notes, and auto-loaded root agent instructions such as
  `CLAUDE.md` and `AGENTS.md`) — **restrained normative voice** under
  BCP 14 (IETF RFC 2119 and RFC 8174). Binding invariants use `MUST` /
  `MUST NOT` (`REQUIRED`, `SHALL`, `SHALL NOT`); strong overrideable
  defaults use `SHOULD` / `SHOULD NOT` (`RECOMMENDED`,
  `NOT RECOMMENDED`); explicit optional allowances use `MAY` (`OPTIONAL`).
  Per RFC 2119 §6, imperatives MUST be used sparingly — rationale
  (`Why`), motivation, cast descriptions, and examples stay in natural
  prose — and per RFC 8174, lowercase `"must"`, `"should"`, and `"may"`
  retain their ordinary English meaning. Authors MUST NOT harden
  optional or default guidance into `MUST`.
- **`Concept`, `Reference`, `Index`** (the consumer's knowledge tree of
  verified reality, reference records such as `RECORD.md`, and directory
  indexes) — **present-tense indicative voice** describing verified
  built truth. These files MUST contain `0` unquoted ALL-CAPS RFC 2119
  keywords (literal mentions quoting a convention or token sit in quotes
  or backticks).
- **`Register`** (dated logs of lessons, rulings, or open items, such as
  the learnings register) — **dated past-tense provenance** separating
  verifiable occurrence from inference (`Fact:` vs. `Interpretation:`,
  per the learnings-register convention), or explicit open/deferred
  status markers. Verbatim historical quotes and dated entries MUST NOT
  be rewritten retroactively to fit later conventions.
- **`Vision`** (where a consumer maintains a sibling aspirational tree
  beside its knowledge tree) — **causal directional compass voice**
  stating problem, direction, and trade-offs. `Vision` files MUST
  contain `0` unquoted ALL-CAPS RFC 2119 keywords (`0` `MUST` / `SHALL`)
  and SHOULD avoid lowercase normative `"must"` and `"shall"` so
  aspirational notes never impersonate ratified specifications or invite
  untriggered work (constitution, Rule 1).

Episode tapes (`type: Brief | Findings`) follow the episodes convention:
a brief states one authorized episode's requirements and acceptance
checks without overriding committed `Convention` law, and findings
report dated verification evidence.

## Why

Sessions wake with no memory and routinely retrieve individual
paragraphs out of surrounding context. When descriptive notes borrow
`MUST` or aspirational notes read like ratified specs, an agent treats
outdated description as law or unapproved direction as an instruction.
Binding voice to `type` makes epistemic status local to the sentence and
mechanically checkable.
