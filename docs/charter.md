# Vessels — Fleet and Operations Command Agent

Vessels is the Ouroboros fleet command agent, providing multi-asset coordination, dispatch envelope management, and status-receipt aggregation across deployed runtime instances.

## Role in the ecosystem

Vessels is the operational spine of the Ouroboros deployment surface. It maintains a live model of every deployed runtime instance — agent processes, service endpoints, task queues, and their current health states — and provides the command surface through which operators issue dispatch instructions, observe aggregate fleet status, and respond to anomalies. Where individual agents like Terra or Counsel operate within their domain surfaces, Vessels sees across all of them: it knows which agents are running, where, and at what load. It does not interpret domain data; it routes, schedules, and reports. Vessels is the "fleet command" interface — a single pane through which operational decisions (scale-up, drain, redeploy, rollback) are expressed as structured dispatch envelopes.

## Capabilities

- **Fleet-state model**: maintains a continuously updated inventory of deployed agent instances, versions, and health metrics.
- **Dispatch envelope routing**: accepts structured dispatch envelopes from operators or orchestration logic and routes them to the correct runtime targets.
- **Status receipt aggregation**: collects per-instance status receipts from all running agents and assembles them into a coherent fleet-wide snapshot.
- **Multi-asset coordination**: manages scheduling and dependency ordering across heterogeneous asset types — land agents, legal agents, hospitality agents — without coupling to their domain logic.
- **Anomaly surfacing**: detects deviations from expected operational baselines (missing heartbeats, receipt gaps, error-rate spikes) and surfaces them in the fleet dashboard.
- **Rollback and drain orchestration**: expresses rollback and graceful-drain operations as first-class dispatch objects with corresponding receipt chains for audit.

## Inputs / Outputs / Receipts

**Inputs**: dispatch envelopes (operator instructions, orchestrator schedules, health-check triggers), per-agent heartbeat signals, deployment manifests, rollback directives.

**Outputs**: fleet-state snapshots (structured JSON with per-instance health), aggregated status receipts, anomaly alerts, dispatch confirmation envelopes.

**Receipts**: every dispatch operation produces a signed receipt containing the envelope hash, target instance set, dispatch timestamp, and outcome code. These receipts are written to the Ouroboros ledger and constitute the audit trail for all fleet-level actions.

## Lambda invariant boundary

Vessels holds an unusually broad observability surface — it can see all agents — but the Λ invariant enforces a strict separation between observation and intervention. Vessels may report anomalies across any agent domain, but it may not modify domain data, override agent-level decisions, or issue commands that exceed the scope of the originating dispatch envelope. A dispatch envelope must be fully specified before Vessels acts on it; Vessels does not infer intent or expand scope.

The invariant also governs the receipt chain: Vessels must not emit a successful dispatch receipt unless it has confirmed delivery to the target runtime. Speculative or fire-and-forget dispatch is not permitted. This makes the receipt chain a reliable audit artifact — every confirmed receipt corresponds to a confirmed delivery, and gaps in the chain are surfaced as anomalies rather than silently dropped.

## Current state

Alpha. Fleet-state model schema and dispatch envelope format are specified. Status receipt aggregation is implemented for a single-host deployment. Multi-host federation and the fleet dashboard UI surface are under development. Integration tests against the Ouroboros runtime are in progress.

## References

- Ouroboros runtime: <https://github.com/szl-holdings/ouroboros>
- Ouroboros thesis: <https://github.com/szl-holdings/ouroboros-thesis>
- SZL Trust: <https://github.com/szl-holdings/szl-trust>

## Maintainer

Stephen P. Lutar Jr. \<stephen@szlholdings.com\>, ORCID 0009-0001-0110-4173
