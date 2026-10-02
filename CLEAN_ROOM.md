# Clean-room policy

This policy is part of the project's contract, not a guideline. A change that breaks it does not merge, whatever else it does. This file is the source of truth; the pull request template, [CONTRIBUTING.md](CONTRIBUTING.md), and [assets/PROVENANCE.md](assets/PROVENANCE.md) point here.

## Why

All of Atrium's code and art will be made for this project. That way the code can be released under the Apache License 2.0, every asset carries a license recorded in [assets/PROVENANCE.md](assets/PROVENANCE.md), and no file inherits non-commercial or copyleft terms from another project.

## Allowed

- Implementing published open specifications: OpenTelemetry (OTel), AG-UI, the Model Context Protocol (MCP), MCP Apps, A2A, and A2UI.
- Depending on unmodified upstream packages installed through the package manager.
- Reading public documentation and READMEs to understand concepts.

## Not allowed

- Copying, vendoring, porting, or translating source code, by hand or with a tool, from any agent-room, agent-office, or visualizer project. This includes Pixel Agents, Claw3D, Hermes3D, OpenClaw Office, Star-Office-UI, Claude-Office, AgentRoom, AI Town, and similar projects.
- Reusing their sprites, tilesets, or layouts.

These projects are named only to make the rule concrete. Atrium is not affiliated with any of them, and naming them implies no endorsement in either direction.

## Process

- **Attestation.** Every pull request completes the clean-room checklist in the [pull request template](.github/pull_request_template.md). A pull request with an unticked box does not merge.
- **Dependencies.** Third-party code enters only as an unmodified package through the package manager. No vendored or patched copies. CI will produce a CycloneDX SBOM and fail when the dependency tree contains a copyleft or non-commercial license. That gate is planned and not in place yet; until it lands, reviewers check new dependencies by hand.
- **Assets.** Every asset has a row in [assets/PROVENANCE.md](assets/PROVENANCE.md). An asset without a row does not merge.
- **Reporting a breach.** If you believe something in this repository breaks this policy, open an issue that names the file and the source you think it came from. If the breach is confirmed, the affected code or asset is removed.
