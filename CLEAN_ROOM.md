# Clean-room policy

This policy is part of the project's contract, not a guideline. A change that breaks it does not merge, whatever else it does. This file is the source of truth; the pull request template, [CONTRIBUTING.md](CONTRIBUTING.md), and [assets/PROVENANCE.md](assets/PROVENANCE.md) point here.

## Why

All of Atrium's code and art will be made for this project. That way the code can be released under the Apache License 2.0, every asset carries a license recorded in [assets/PROVENANCE.md](assets/PROVENANCE.md), and no file inherits non-commercial or copyleft terms from another project.

## Allowed

- Implementing published open specifications: OpenTelemetry (OTel), AG-UI, the Model Context Protocol (MCP), MCP Apps, A2A, and A2UI. You may read these specifications and their reference code. Code from them still enters Atrium only as an unmodified dependency.
- Depending on unmodified upstream packages installed through the package manager.
- Reading public documentation, READMEs, and published specs to understand concepts, including those of the listed projects below.

## Not allowed

- Copying, vendoring, porting, or translating source code, by hand or with a tool, from any agent-room, agent-office, or visualizer project. This includes Pixel Agents, Claw3D, Hermes3D, OpenClaw Office, Star-Office-UI, Claude-Office, AgentRoom, and AI Town (the **listed projects**), and similar projects.
- Reusing their sprites, tilesets, or layouts.
- Reading the source code of a listed project while you work on Atrium. The same applies to any AI coding agent working for you.
- Giving the source code of a listed project to a tool (an AI assistant, a code search, a translator) to produce Atrium code.

These projects are named only to make the rules concrete. Atrium is not affiliated with any of them, and naming them implies no endorsement in either direction.

## Process

- **Attestation.** Every pull request completes the clean-room checklist in the [pull request template](.github/pull_request_template.md). A pull request with an unticked box does not merge. Bot dependency updates are the one exception (see below).
- **Prior exposure.** If you have read the source code of a listed project at any time, say so in your pull request. Maintainers may ask you to work on a different component.
- **Dependencies.** Third-party code enters only as an unmodified package through the package manager. No vendored or patched copies. CI will produce a CycloneDX SBOM and check every license in the dependency tree against an allowlist, failing on copyleft, non-commercial, or unknown licenses (the **license gate**). That gate is planned and not in place yet; until it lands, reviewers check new dependencies by hand.
- **Assets.** Every asset has a row in [assets/PROVENANCE.md](assets/PROVENANCE.md). An asset without a row does not merge.
- **AI-generated assets.** An AI-generated asset is accepted only when DCYFR Labs commissions it: a DCYFR Labs maintainer produces it, or DCYFR Labs approves it in advance in an issue that its ledger row links to. It is labeled "AI-generated", with the tool named, wherever it is listed or credited. Its prompt must not name any agent-room, agent-office, or visualizer project, or ask to imitate their art. [assets/PROVENANCE.md](assets/PROVENANCE.md) describes the ledger row and the labelling.
- **Bot dependency updates.** This rule takes effect once the repository has a package manifest. A pull request that a bot opens (for example Dependabot) and that changes only package manifests and lockfiles is exempt from the clean-room checklist and from DCO sign-off, since a bot cannot sign off. The license gate stands in for the checklist: it is a required check, and the pull request does not merge until it passes. Until the license gate exists, these pull requests do not merge. A bot pull request that changes any other file needs a human to complete the checklist.
- **Reporting a breach.** If you believe something in this repository breaks this policy, open an issue that names the file and the source you think it came from. If the breach is confirmed, the affected code or asset is removed.
