# Architecture — DistilOps Control Plane

## Goal
Provide an internal portal to operationalize model distillation with:
- lineage + reproducibility
- SLO-based release gating
- Responsible AI gate
- incidents + auditability

## Components
- Control Plane UI (UI Bakery hosted)
- Mock API layer (in-memory, contract-first)
- Future integrations: Azure ML pipelines, telemetry, model registry

## High-level flow
Dataset → Teacher → Distill Config → Student Artifact → Eval Report → RAI Gate → Release Gate → Promotion

## Reliability
- Gate decisions are explainable and reproducible (config snapshots)
- Monitoring includes burn-rate and time-to-breach
- Incidents link back to affected run/model versions

## Security basics
- Role-based UX: Viewer (read-only), Operator (operate runs), Approver (promotion)
- Audit log for all actions with request_id
