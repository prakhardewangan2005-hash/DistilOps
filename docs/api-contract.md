# API Contract (Backend Swappable)

This UI is contract-first. Replace mock API with real services without UI changes.

## Entities

### Run
- run_id: string
- dataset: string
- dataset_version: string
- teacher_id: string
- student_id: string
- config: object (temperature, alpha, epochs, seed)
- status: queued|running|succeeded|failed
- created_at: ISO timestamp
- created_by: string

### Metrics
- run_id: string
- teacher_accuracy: number
- student_accuracy: number
- accuracy_delta: number
- f1: number
- ece: number
- drift_score: number
- model_size_mb: number
- p50_ms: number
- p95_ms: number
- error_rate: number
- availability: number
- cost_usd: number
- updated_at: ISO timestamp

### GateStatus
- run_id: string
- release_gate: pass|blocked
- blockers: string[]
- checks: { latency: pass|fail, rai: pass|fail, drift: pass|fail, fairness: pass|fail }
- burn_rate: { latency: number, error_rate: number }
- time_to_breach: { latency: string, error_rate: string }

### Incident
- incident_id: string
- sev: SEV0|SEV1|SEV2|SEV3
- status: open|mitigating|resolved
- impact: string
- linked_run_id: string
- owner: string
- started_at: ISO timestamp
- resolved_at: ISO timestamp|null

### AuditEvent
- request_id: string
- actor: string
- role: Viewer|Operator|Approver
- action: string
- entity_type: run|incident|approval|rai
- entity_id: string
- timestamp: ISO timestamp

### Approval
- run_id: string
- reviewer: string
- decision: approve|reject
- comment: string
- timestamp: ISO timestamp

## Endpoints (Suggested)
- GET /runs
- GET /runs/{run_id}
- GET /runs/{run_id}/lineage
- GET /metrics/{run_id}
- GET /gates/{run_id}
- GET /incidents
- POST /incidents
- GET /audit
- POST /approvals
