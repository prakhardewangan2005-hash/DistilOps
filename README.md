# DistilOps — ML Control Plane for Model Distillation
**Internal-Style AI Engineering Platform**

DistilOps is an internal ML **Control Plane** for operationalizing **model distillation**. It focuses on *safe promotion*, *observability*, *Responsible AI enforcement*, and *release gating*—treating distillation as a **production decision**, not just a training step.

---

## Live Demo
**Production:**  
https://cloud.uibakery.io/special-roast-carapils-dormammu/cOqOKZmn0Pbhai

Demo Mode: Mock API enabled (contract-first design). Backend services (Azure ML, telemetry, monitoring) can be integrated without UI changes.

---

## 2-Minute Demo Walkthrough
If you only have 2 minutes, follow this exact click path:  
Overview → Release Gate → Run Lineage → Incidents → Audit Log → Responsible AI → Runbook  
Full walkthrough available in `docs/demo-walkthrough.md`.

---

## Why DistilOps Exists
Model distillation reduces cost and latency—but introduces risks such as accuracy regressions, fairness gaps, SLO breaches, and unclear lineage or approvals. DistilOps addresses these risks by embedding governance and operational controls directly into the ML lifecycle.

---

## Core Capabilities
Release Gate (Ship / No-Ship): SLO-based gating on p95 latency, error rate, and availability with explicit block reasons and burn-rate visibility.  
Run Lineage & Reproducibility: Dataset → Teacher → Config → Student → Evaluation → Promotion with deterministic configs (seed, dataset version, hyperparameters) and artifact integrity metadata.  
Inference Monitoring & Incidents: p50/p95 latency, error rate, availability with alert-driven incident creation and SEV levels.  
Responsible AI Gate: Slice-based fairness checks, intended use and limitations required; promotion blocked until RAI passes.  
Audit Logs & Approvals: Immutable audit trail for all actions, role simulation (Viewer / Operator / Approver), approval justification required.  
Runbooks: Drift handling, latency regressions, fairness failures, and on-call escalation guidance.

---

## System Design (High Level)
Dataset → Teacher Model → Distillation Config (seed, params) → Student Model → Evaluation + RAI Gate → Release Gate (SLOs) → Promotion / Block → Inference Monitoring → Incidents → Audit Log

---

## Example Metrics (Demo)
Teacher Accuracy: 93.2%  
Student Accuracy: 89.7%  
Accuracy Delta: −3.5%  
Model Size: 67.3 MB  
p95 Latency: 28.7 ms (Target: 25 ms → Blocked)  
Error Rate: 1.2%  
Availability: 99.9%

---

## Responsible AI Principles
Fairness evaluated before promotion, limitations documented, decisions logged and reviewable, and Responsible AI enforced as a **hard release gate** rather than a checklist.

---

## Why Mock API Mode
This project intentionally runs in Mock API Mode to validate workflows and UX, simulate real enterprise ML operations, and keep the demo self-contained. The backend contract is defined and can be swapped with real services without UI redesign.

---

## Repository Structure
docs/: architecture.md, api-contract.md, responsible-ai.md, runbook.md, demo-walkthrough.md  
evidence/: metrics.sample.json, run.sample.json, incident.sample.json, audit.sample.json

---

## Future Extensions
Azure ML pipeline integration  
Real-time drift detection  
Automated retraining triggers  
Cost-aware promotion policies

---

## Key Takeaway
DistilOps is not a dashboard. It is a **decision system** for safely promoting distilled models into production.

---

© 2026 — DistilOps (Internal ML Engineering Prototype)
