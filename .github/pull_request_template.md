## Summary

<!-- What does this change do, and why? Link the issue it addresses, for example "Closes #12". -->

## Testing

<!-- What did you run, and what did it show? For a documentation-only change, say so. -->

## Clean-room attestation

Tick every box. A pull request with an unticked box does not merge. The policy is in [CLEAN_ROOM.md](https://github.com/dcyfr-labs/atrium/blob/main/CLEAN_ROOM.md).

- [ ] This change contains no source copied, vendored, ported, or translated (by hand or with a tool) from any agent-room, agent-office, or visualizer project, including those listed in CLEAN_ROOM.md.
- [ ] This change reuses no sprites, tilesets, or layouts from those projects.
- [ ] Every asset this change adds or modifies has a row in [assets/PROVENANCE.md](https://github.com/dcyfr-labs/atrium/blob/main/assets/PROVENANCE.md), or the change adds no assets.
- [ ] Every dependency this change adds is an unmodified upstream package installed through the package manager, or the change adds no dependencies.
- [ ] Every commit carries a DCO `Signed-off-by` line (`git commit -s`), as described in [CONTRIBUTING.md](https://github.com/dcyfr-labs/atrium/blob/main/CONTRIBUTING.md).
