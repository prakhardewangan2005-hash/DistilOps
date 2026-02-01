# DistilOps — 2-Minute Recruiter Demo Walkthrough

This walkthrough is designed for a **2-minute recruiter / interviewer demo** to quickly understand
how DistilOps operationalizes **model distillation** with reliability, Responsible AI, and release governance.

Live Demo:
https://cloud.uibakery.io/special-roast-carapils-dormammu/cOqOKZmn0Pbhai

---

## 0:00–0:20 — Overview (Release Gate & SLOs)
**Path:** Overview

- Start on the **Overview** page.
- Highlight the **Release Gate banner**:
  - Status: *BLOCKED*
  - Reasons: p95 latency breach, fairness gap
- Explain that **promotion decisions are automated and explainable**, not manual.

**Key takeaway:**  
DistilOps treats model distillation as a *ship/no-ship decision system*, not just training.

---

## 0:20–0:40 — Run Lineage (Reproducibility)
**Path:** Run Lineage → Select run `run-0001`

- Show the **end-to-end lineage**:
- Point out:
- dataset version
- seed + hyperparameters
- artifact integrity (IDs / timestamps)

**Key takeaway:**  
Every model is **reproducible and auditable**.

---

## 0:40–1:00 — Incidents (Ops Reality)
**Path:** Incidents

- Show an incident linked to a model/run.
- Explain:
- SEV level
- impact
- ownership
- Emphasize linkage between **monitoring → incident → affected run**.

**Key takeaway:**  
Model failures are treated like **production incidents**, not offline metrics.

---

## 1:00–1:20 — Audit Log (Compliance)
**Path:** Audit Log

- Scroll through audit events:
- promotions
- approvals
- RAI decisions
- Highlight:
- request_id
- actor + role
- timestamp

**Key takeaway:**  
Every decision is **traceable**, which is critical for enterprise AI systems.

---

## 1:20–1:40 — Responsible AI Gate
**Path:** Responsible AI

- Show **RAI checklist** tied to the run.
- Call out:
- fairness slices
- limitations
- intended / out-of-scope use
- Explain that **RAI failures block promotion automatically**.

**Key takeaway:**  
Responsible AI is a **hard gate**, not a documentation checkbox.

---

## 1:40–2:00 — Runbook (On-Call Readiness)
**Path:** Runbook

- Open “Handling Model Drift Alert”.
- Show step-by-step operational guidance.
- Emphasize:
- escalation logic
- retraining triggers
- promotion rules

**Key takeaway:**  
DistilOps is designed for **real on-call engineers**, not demos.

---

## Final One-Line Summary
> “DistilOps shows how distilled models move from experimentation to production safely—with lineage, SLOs, Responsible AI, and auditability built in.”

---

**Demo Mode Note:**  
This demo runs in **Mock API Mode** with a contract-first backend design.
The UI can be connected to Azure ML pipelines and telemetry without redesign.
