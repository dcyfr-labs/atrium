# AGENTS.md

Atrium is a planned local-first, runtime-agnostic control plane and spatial client for AI agents, from DCYFR Labs. **The repository is at the design stage: there is no code, no manifest, no tests, no CI and no release.** Do not invent commands for any of those.

## What exists

```
README.md                         the design: principles, planned components, out of scope for v1
CLEAN_ROOM.md                     the clean-room policy; source of truth, a breach does not merge
CONTRIBUTING.md                   design-stage contribution rules, DCO sign-off
SECURITY.md                       private vulnerability reporting
assets/PROVENANCE.md              asset ledger; currently "No assets yet."
.github/pull_request_template.md  Summary, Testing, and the clean-room attestation
LICENSE, NOTICE                   Apache-2.0
```

There is no OpenSpec directory in this repository. The design lives in `README.md`. Everything the README lists under "Planned components" is a plan, not a feature.

## Rules for contributing at this stage

- **Open an issue first.** Design discussion is the useful contribution. Small documentation fixes (typos, broken links) can go straight to a pull request. Hold code pull requests until the repository has a code layout and CI.
- **Clean room.** Read `CLEAN_ROOM.md` before touching anything. Copy, vendor, port or translate nothing from agent-room, agent-office or visualizer projects, and do not read the source of the projects it lists (the same applies to an AI agent working for you). Third-party code may only arrive as an unmodified package-manager dependency.
- **DCO.** Every commit you author needs a `Signed-off-by` line whose name and email match the commit author (`git commit -s`). Dependency-update bot commits and GitHub-created merge commits are exempt.
- **Assets.** Every asset file needs a row in `assets/PROVENANCE.md` in the same pull request. AI-generated assets need prior approval from a DCYFR Labs maintainer in an issue, a label naming the tool, and a clean prompt. Describe AI art by style and tool, never with craft verbs such as painted, drawn or illustrated.
- **Pull requests.** Fill in `.github/pull_request_template.md`, including every clean-room box; a PR with an unticked box does not merge. Keep one change per PR.
- **Keep the status line true.** The README states "Status: design stage" and phrases every component as planned. If you edit the README, keep future tense for anything that does not exist.

## Verifying a change

There is nothing to build or test. For a documentation change, check that every relative link resolves (`ls` the target) and that you changed no statement about what exists.

## Never

- Add code, a package manifest or a CI workflow in a documentation PR.
- Commit secrets or tokens.
- Use or paraphrase material from the projects listed in `CLEAN_ROOM.md`.
- Add an asset without a provenance row.
- Push to `main`.
