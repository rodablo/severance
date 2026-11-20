# No user-specific or hardcoded absolute paths

Two rules, both about keeping a repo decoupled from *where* and *by
whom* it happens to be checked out.

## Rule 1 — never commit a username or user-home path

Tracked files MUST NOT contain a **user-specific absolute path** — a
real login name or a `/home/<login>/…` (or `/Users/<login>/…`,
`C:\Users\…`) path.

- **Docs/links:** use **repo-relative** paths — never
  `file:///home/<login>/…` links.
- **Prose that must illustrate a home path:** use the `<user>`
  placeholder (`/home/<user>/…`), never a real login.
- **Applies even to comments and disabled scratch code.** A committed
  username changes *no behavior* there, but it still ships in every
  clone and is grep-visible — a privacy leak and a needless
  personalization of the tree. Strip the path (make it relative) or
  delete the dead line.
- **Not covered:** a **fixed** non-personal user baked into tooling
  (e.g. a dev container's standard `vscode` user) is not a personal
  login — it's the same on every machine, portable, and intentional.
  Only *personal* logins and host-home paths are forbidden.
- **Check before committing** (both MUST be empty):
  ```sh
  git grep -iE '/(home|Users)/[A-Za-z0-9_.-]+/' | grep -vE '/home/<fixed-tool-user>/'  # → empty
  git grep -i '<your-login>'                                                            # → empty
  ```

## Rule 2 — never hardcode the workspace/checkout path; derive it

The location and folder name of the checkout MUST NOT be baked into
tracked files:

- **Build tooling:** MUST derive roots from the invocation (`$(PWD)` +
  `realpath` or equivalent) so builds run from **any** path — including
  ephemeral worktrees.
- **Container plumbing:** MUST derive from the container tooling's
  variables (e.g. a devcontainer's `${localWorkspaceFolderBasename}` /
  `${containerWorkspaceFolder}`), expose a `WORKSPACE_ROOT`-style env
  var, and make scripts/guards read **that** — never a literal path.
  Worktree parents derive from it. Git hooks stay path-free by design
  (compare `git rev-parse --absolute-git-dir` with `--git-common-dir`).

## Why

- **Portability:** clone anywhere, name the folder anything, and the
  container + build + guards work unchanged — a repo rename needs
  **zero** code edits. (Proven in the first consumer: the repo was
  renamed without touching code.)
- **Privacy:** no contributor's login ships to everyone who clones.
- **Reproducibility:** no hidden dependency on one machine's directory
  layout.
