# Alert Triage

## Objective

To analyze and prioritize alerts based on severity and impact.

## Alert Summary

Failed login attempts were detected using Event ID 4625.

## Analysis

- Multiple failed login attempts observed  
- No confirmed successful unauthorized access  
- Activity appears suspicious but not critical  

## Severity

Medium

## Decision

Alert requires monitoring but does not need immediate escalation.

## Alert Details

| Field | Value |
|------|------|
| Alert ID | ALT-001 |
| Event | Failed Login |
| Source | Windows Logs |
| Event ID | 4625 |
| Severity | Medium |

## Reasoning

- Multiple failed login attempts observed  
- No confirmed successful compromise  
- Activity suspicious but not critical  

## Decision

Monitor activity. Escalate if:
- login succeeds
- attempts increase
## Screenshot

<img width="1257" height="948" alt="Screenshot 2026-04-07 210558" src="https://github.com/user-attachments/assets/f50661c7-cac7-4e81-9fc1-743037d9c238" />
