# Log Analysis

## Objective
The objective of this task is to analyze system and authentication logs in order to identify suspicious or malicious activities, such as unauthorized access attempts, abnormal login behavior, and unusual patterns.

## What I Will Do

* Review login attempts
* Identify failed logins
* Look for unusual IP addresses
* Detect suspicious patterns

## Tools (conceptual)

* SIEM tools (like Splunk)
* Log files

## Outcome

Identify whether activity is normal or suspicious.

Methodology
1. Review Login Attempts
  Examined authentication logs containing:
      Username
      Timestamp
      IP address
      Login status (Success/Failure)
  Focused on identifying:
      Frequency of login attempts
      Time distribution (day/night activity)
      Repeated attempts by same user/IP

2. Identify Failed Logins
   Extracted all failed login attempts
   Key observations:
      Multiple failed attempts for specific accounts
      Repeated failures from same IP addresses
  This may indicate:
      Brute-force attacks
      Credential guessing attempts

3. Analyze IP Addresses
    Reviewed source IP addresses for:
      Geographic location (if available)
      Known vs unknown IPs
  Identified:
      IPs not previously associated with users
      IPs making multiple login attempts in short time

4. Detect Suspicious Patterns
    Patterns analyzed include:
      Multiple failed logins followed by a success (possible compromise)
      Logins from different locations within short time (impossible travel)
      High frequency of login attempts in seconds/minutes
      Access attempts during unusual hours (late night/early morning)

  Tools Used (Conceptual)
      SIEM Tools (e.g., Splunk)
      Used for:
        Log aggregation
        Search queries
        Pattern detection
        
      Example query (conceptual):
          index=auth_logs status=failed
          | stats count by user, ip
          | where count > 5

  Log Files
    Types analyzed:
        Authentication logs
        System logs
        Application logs
      
## Sample Log Data (Example)

| Timestamp        | Username | IP Address    | Status  |
| ---------------- | -------- | ------------- | ------- |
| 2026-04-08 09:01 | user1    | 192.168.1.10  | Success |
| 2026-04-08 09:05 | user2    | 203.0.113.45  | Failed  |
| 2026-04-08 09:06 | user2    | 203.0.113.45  | Failed  |
| 2026-04-08 09:07 | user2    | 203.0.113.45  | Success |
| 2026-04-08 02:30 | admin    | 198.51.100.22 | Success |

Findings
1. Multiple Failed Login Attempts
    User: user2
    IP: 203.0.113.45
    Behavior:
        Repeated failed attempts followed by success
    Suspicion: Possible brute-force attack

2. Unusual Login Time
    User: admin
    Time: 02:30 AM
    Suspicion: Login outside normal working hours

3. Unknown IP Address Activity
    IP: 198.51.100.22
    Not recognized in normal access patterns
    Suspicion: Unauthorized access attempt

4. Rapid Login Attempts
      Multiple login attempts within seconds
      Indicates automated attack (bot/script)

### Analysis
  Based on the observations:

| Activity Type          | Risk Level | Explanation                       |
| ---------------------- | ---------- | --------------------------------- |
| Repeated failed logins | High       | Brute-force attempt likely        |
| Unknown IP access      | Medium     | Needs verification                |
| Odd login timing       | Medium     | Could be legitimate or suspicious |
| Normal login patterns  | Low        | Regular user activity             |


### Conclusion
The log analysis indicates potential suspicious activity, including:

Brute-force login attempts
Access from unknown IP addresses
Login attempts during unusual hours

While some activities may be legitimate, the presence of these patterns suggests a moderate to high security risk.

Recommendations

To improve security:

    Enable multi-factor authentication (MFA)
    Implement account lockout policies after failed attempts
    Monitor logs continuously using SIEM tools
    Restrict access from unknown or foreign IP addresses
    Set alerts for:
      Multiple failed login attempts
      Logins at unusual hours



### Outcome

After analyzing the logs:
Some activities were normal, but several patterns were identified as suspicious and potentially malicious, requiring further investigation and preventive measures.

## Real Log Analysis (Practical Work)

### What I did
I generated failed login attempts on my system and analyzed real Windows security logs.

### Steps followed
- Opened Event Viewer → Windows Logs → Security
- Filtered logs using Event ID 4625 (failed login attempts)
- Exported logs to a file (real_logs.txt)
- Used command line tool (findstr) to filter relevant entries

### Command used
findstr "4625" real_logs.txt

### What I observed
- Multiple failed login attempts were recorded
- Event ID 4625 indicates failed login activity
- Logs include timestamp, logon type, and system details

### My understanding
Repeated failed login attempts could indicate:
- Incorrect password attempts
- Unauthorized access attempts
- Possible brute-force behavior if repeated frequently

This kind of activity should be monitored in a SOC environment.

## Splunk Analysis

Logs were ingested into Splunk and analyzed using search queries.

Query Used:
index=* EventCode=4625

Observation:
Multiple failed login attempts were detected in Splunk, confirming earlier analysis.

