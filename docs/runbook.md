# Runbook

## Handling model drift alert (Critical)
1. Check Inference Monitoring for drift_score breach
2. Compare metrics vs baseline in Run Lineage
3. Inspect recent input distribution shifts
4. If drift_score > 0.05 for 7d → trigger retrain/distill cycle
5. Use latest dataset version with validated quality
6. Promote only after RAI Gate passes and approval is recorded

## Handling p95 latency regression
1. Confirm p95 breach and burn rate
2. Check model version + recent changes
3. Roll back to last known good candidate if customer impact
4. Open SEV incident if SLO breach sustained

## Handling fairness gate failure
1. Identify failing slice and magnitude
2. Verify dataset representativeness
3. Consider thresholding/abstention or additional training data
4. Document limitations in model card and re-run evaluation
