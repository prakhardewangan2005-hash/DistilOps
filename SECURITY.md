# Security Policy

## Reporting a Vulnerability
If you discover a security issue, please do not open a public issue.
Instead, contact the maintainer with details and reproduction steps.

## Scope
This repository contains an internal-style control plane prototype and documentation.
No production secrets are stored here. Demo uses mock data.

## Secure-by-default Practices
- No hardcoded credentials
- Role simulation for least-privilege UX flows (Viewer/Operator/Approver)
- Input validation expectations documented in the API contract
