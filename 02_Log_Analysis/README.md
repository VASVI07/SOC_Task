# Log Analysis

## Objective

Analyze logs to identify suspicious or malicious activity.

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

## Sample Log Analysis

### Logs Observed

User: admin | IP: 192.168.1.10 | Status: Failed Login

User: admin | IP: 192.168.1.10 |status: Failed Login

User: admin | IP: 192.168.1.10 | Status: Success

### Analysis

* Multiple failed login attempts detected
* Same IP address used repeatedly
* Successful login after failures

### Conclusion
This may indicate a brute force attack attempt.
Further investigation is recommended to confirm malicious activity.


This may indicate a brute force attack attempt.

## Command Line Analysis


### Command Used

findstr "Failed" sa<img width="1115" height="1321" alt="Screenshot 2026-04-07 204755" src="https://github.com/user-attachments/assets/dfbc6a58-1bb2-4303-8d85-c9a7b5d64cc3" />
mple_logs.txt

### Result

Filtered failed login attempts from log file.

### Conclusion

Multiple failed login attempts detected, indicating possible suspicious activity.

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
