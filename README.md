# Atrium

Atrium is a planned local-first, runtime-agnostic control plane and spatial client for AI agents, from DCYFR Labs. The goal is one place where an operator can observe, direct, approve, isolate, and replay agents that run on different runtimes.

> **Status: design stage.** There is no code, no release, and no published package yet. The design below is a plan, and the plan will change.

## The idea: rooms are security boundaries

In the agent "room" and "office" visualizers we have looked at, a wall or a door in the scene does not correspond to any real boundary. Atrium's design starts from the opposite rule: what the room shows must be what the system enforces.

- A **room** is a sandbox profile, an egress policy, a credential scope, and a data-classification (TLP) ceiling.
- **Moving an agent into a room** is a policy-checked command that re-issues the agent's scoped credentials.
- A **locked door** is a policy deny.
- The view will show **only state that an event backs**, labeled with its source and its age. Stale or inferred state will be drawn as degraded.

## Design principles

- **Tell the truth.** Every rendered state will carry its source, when it was observed, and a confidence value. Errors and retries will be first-class parts of the view.
- **Control as well as observe.** Spawn, pause, resume, kill, reassign, set budgets, and approve. Every command will be signed, policy-checked, and audited.
- **Local-first and secure by default.** Bind to `127.0.0.1` by default, never put tokens in URLs, and reach remote hosts only through an overlay network the operator sets up. If Atrium stops, the agents will keep running.
- **Build on open standards.** Implement open specifications directly (OpenTelemetry GenAI conventions, AG-UI, MCP, MCP Apps, A2A, A2UI) and use upstream libraries only as unmodified dependencies.
- **Event-sourced.** One append-only event log will back the live view, replay, and audit.
- **Two views.** A non-spatial Console view will ship alongside the spatial Room view, for accessibility and dense operations.

## Planned components

Every item here is planned. None of it exists yet, and the names may change.

- **Event schema.** Atrium Room Events (ARE): a versioned event envelope with provenance fields, plus a mapping from events to what the Room and Console views show. Aligned with OpenTelemetry GenAI span names and AG-UI event names.
- **Gateway.** Event ingest, the event log, world-state projection, a signed command API, policy checks, approvals, and an AG-UI endpoint.
- **Adapters.** Observe-only adapters for agent runtimes, for example `@dcyfr/ai`, Claude Code hooks, JSONL transcripts, OTLP, and A2A peers. Each adapter declares how much its events can be trusted.
- **Runner.** A sandbox supervisor that enforces room profiles: filesystem, egress allowlist, resource quotas, and scoped secrets.
- **Inference broker.** A local model broker with per-agent budgets and usage meters.
- **Memory inspector.** View, quarantine, and delete agent memory, with provenance and taint tags.
- **Client.** The Console view, the Room view on a small in-house 2D engine, timeline replay, and an approvals inbox.
- **Generative UI host.** Catalog-only A2UI rendering and sandboxed MCP Apps views.
- **SDK and CLI.** Room and plugin manifests, an adapter SDK, and a command-line tool.

## Out of scope for v1

- Forking or porting any existing agent-room or agent-office project (see [CLEAN_ROOM.md](CLEAN_ROOM.md)).
- A 3D renderer, VR or AR, or a mobile-native client.
- A hosted service or an internet-facing multi-tenant deployment.
- Real-time collaboration between several human operators. v1 has one operator; read-only observers are optional.
- Voice input and output.
- Model training, or replacing local model servers such as Ollama or llama-server.
- WebMCP browser integration.

## Contributing

While Atrium is at the design stage, the most useful contribution is an issue about the design. Read [CONTRIBUTING.md](CONTRIBUTING.md) before opening a pull request. Every commit you author needs a DCO sign-off.

## Clean room

All of Atrium's code and art will be made for this project. Nothing may be copied or ported from other agent-room projects. The policy is in [CLEAN_ROOM.md](CLEAN_ROOM.md), every pull request attests to it, and asset provenance is recorded in [assets/PROVENANCE.md](assets/PROVENANCE.md).

## Security

Report vulnerabilities privately, not in public issues. See [SECURITY.md](SECURITY.md).

## License

Apache License 2.0. See [LICENSE](LICENSE) and [NOTICE](NOTICE). Each asset's license is recorded in its row in [assets/PROVENANCE.md](assets/PROVENANCE.md).
