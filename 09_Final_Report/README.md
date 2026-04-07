# Final SOC Report

## Summary

This project involved analyzing suspicious login activity using real Windows logs.

---

## Investigation Steps

- Log analysis performed using Event Viewer  
- Failed login attempts identified (Event ID 4625)  
- Logs correlated based on timestamps  
- Anomalies detected (rapid login failures)  
- IP analyzed using VirusTotal and AbuseIPDB  

---

## Key Findings

- Multiple failed login attempts detected  
- Activity occurred within seconds  
- IP identified as malicious  
- Behavior indicates brute force attempt  

---

## Actions Taken

- Alert triaged as medium severity  
- Incident documented  
- Evidence preserved  
- Monitoring recommended  

---

## Conclusion

The investigation identified suspicious login activity consistent with brute force behavior. While no confirmed compromise occurred, the activity requires monitoring and possible mitigation.
