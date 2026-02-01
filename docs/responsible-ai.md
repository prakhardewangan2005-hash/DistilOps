# Responsible AI Gate (RAI)

## Purpose
Prevent unsafe promotion of distilled models by enforcing documentation and slice checks.

## Required checks before promotion
- Intended use and out-of-scope use documented
- Known limitations & failure modes documented
- Slice-based fairness metrics reviewed (>= 3 slices)
- Privacy and data handling notes included
- Reviewer approval logged

## Example slices
- Input length bucket (short/medium/long)
- Topic/label category
- Source channel bucket (if applicable)

## Gate behavior
- If fairness_gap fails → Release Gate = BLOCKED
- If required documentation missing → Release Gate = BLOCKED
- All decisions must be recorded in audit log
