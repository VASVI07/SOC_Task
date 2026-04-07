# Capstone Project — Security Incident Investigation

## Scenario

During routine log monitoring, multiple failed login attempts were detected in the Windows Security logs (Event ID 4625). These attempts occurred within a very short time frame, indicating abnormal behavior.

---

## Step 1: Log Analysis

The system logs were analyzed using exported Windows Security logs.

Findings:
- Multiple failed login attempts observed
- Events occurred within seconds
- Event ID: 4625 (Failed Login)

This pattern suggested possible brute force activity.

---

## Step 2: Log Correlation

The failed login events were correlated based on timestamps.

Observation:
- Repeated login failures occurred within seconds
- Activity pattern indicates automated attempts rather than manual login

---

## Step 3: Anomaly Detection

The behavior was identified as anomalous due to:
- High frequency of login failures
- Short time interval between attempts

This is not typical for normal user activity.

---

## Step 4: Threat Intelligence

The associated IP address was analyzed using external threat intelligence tools:

Tools Used:
- VirusTotal
- AbuseIPDB

Findings:
- IP flagged as malicious by multiple vendors
- High abuse confidence score
- Identified as suspicious (possible Tor exit node)

---

## Step 5: Alert Triage

Severity: Medium

Reason:
- Suspicious login attempts detected
- No confirmed successful unauthorized access

Decision:
- Monitor activity closely
- No immediate escalation required at this stage

---

## Step 6: Incident Escalation

Criteria for escalation:
- If login attempts continue
- If a successful login is observed
- If multiple systems are targeted

Current Status:
- Escalation not required yet
- Kept under monitoring

---

## Step 7: Evidence Preservation

The following evidence was collected and preserved:
- Exported Windows Security logs
- Command line analysis outputs
- Screenshots of log activity
- Threat intelligence results

All evidence was stored securely for future investigation.

---

## Final Conclusion

The investigation identified multiple failed login attempts consistent with brute force behavior. Threat intelligence confirmed the associated IP as potentially malicious.

Although no successful compromise was observed, the activity is suspicious and requires continued monitoring.

---
