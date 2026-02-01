# Changelog

## 0.2.0 — 2026-02-02
### Added
- Release Gate banner with SLO-based block reasons (p95 latency, error rate, availability)
- Run Lineage page (dataset → teacher → distill config → student → eval → promotion candidate)
- Incidents page with SEV levels and lifecycle tracking
- Audit Log page with request_id traceability
- Responsible AI (RAI) Gate enforced before promotion
- Runbook page for drift, latency regressions, and fairness violations
- Role simulation: Viewer / Operator / Approver
- Command palette search (Ctrl+K)

### Notes
- Demo runs in Mock API Mode (contract-first UI). Backend integration planned via API contract.
