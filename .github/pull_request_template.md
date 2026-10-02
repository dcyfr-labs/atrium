## Summary

<!-- What does this change do, and why? Link the issue it addresses, for example "Closes #12". -->

## Testing

<!-- What did you run, and what did it show? For a documentation-only change, say so. -->

## Clean-room attestation

Tick every box. A pull request with an unticked box does not merge. The policy is in [CLEAN_ROOM.md](https://github.com/dcyfr-labs/atrium/blob/main/CLEAN_ROOM.md). A dependency-update pull request opened by a bot follows the bot rule in CLEAN_ROOM.md instead of this checklist.

- [ ] This change contains no source copied, vendored, ported, or translated (by hand or with a tool) from any agent-room, agent-office, or visualizer project, including those listed in CLEAN_ROOM.md.
- [ ] This change reuses no sprites, tilesets, or layouts from those projects.
- [ ] I have not read the source code of a project listed in CLEAN_ROOM.md while working on this change, and no tool (including an AI coding agent) did so on my behalf.
- [ ] I have never read the source code of a listed project, or I say in the summary above that I have.
- [ ] Every asset this change adds or modifies has a row in [assets/PROVENANCE.md](https://github.com/dcyfr-labs/atrium/blob/main/assets/PROVENANCE.md), or the change adds no assets.
- [ ] Any third-party code in this change arrives as an unmodified upstream package installed through the package manager, with no vendored, copied, or patched copies, or the change adds no third-party code.
- [ ] Every commit carries a DCO `Signed-off-by` line (`git commit -s`), as described in [CONTRIBUTING.md](https://github.com/dcyfr-labs/atrium/blob/main/CONTRIBUTING.md).
