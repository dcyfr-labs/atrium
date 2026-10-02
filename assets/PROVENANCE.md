# Asset provenance

Every asset file in this repository has one row in the ledger below. Assets include images, sprites, tilesets, room layouts, fonts, audio, and any other non-code media. **An asset without a row does not merge.** This ledger is part of the clean-room contract in [CLEAN_ROOM.md](../CLEAN_ROOM.md).

## Rules

- One row per file, added in the same pull request as the file. Changing an asset updates its row.
- **Asset path** is relative to the repository root.
- **Author or creator** names the person or organization responsible for the asset. For a generated asset, name the person who ran the tool.
- **Source** is one of:
  - `original`: made for Atrium by the named author.
  - `commissioned`: made for Atrium by the named author under a commission. The notes say who holds the agreement.
  - `generated with <tool>`: produced with an AI tool. Record the tool and model version, and a prompt reference (the prompt text, or the path to it in this repository).
- **License** is an SPDX identifier. The license must allow commercial use and modification and must not be share-alike: for example `Apache-2.0`, `CC0-1.0`, or `CC-BY-4.0`. Non-commercial, no-derivatives, and copyleft terms are not accepted. For a generated asset, the tool's terms must also allow commercial use of its output.
- **Date added** is `YYYY-MM-DD`.
- **Notes** describe what the asset shows. Describe a generated asset by its style and the tool that produced it, never with verbs that imply a human hand (painted, drawn, illustrated, airbrushed).
- Assets from agent-room, agent-office, or visualizer projects are never accepted, whatever their license (see [CLEAN_ROOM.md](../CLEAN_ROOM.md)).

Example rows (not real assets):

```text
| assets/rooms/lab-01/floor.png | Example Author | original | Apache-2.0 | 2026-11-02 | Floor tiles, 32 px grid |
| assets/rooms/lab-01/desk.png | Example Operator | generated with ExampleTool model-x 1.2 (prompt: assets/prompts/lab-01-desk.txt) | Apache-2.0 | 2026-11-02 | Flat-shaded desk sprite, 4 directions |
```

## Ledger

| Asset path | Author or creator | Source | License | Date added | Notes |
|---|---|---|---|---|---|

No assets yet.
