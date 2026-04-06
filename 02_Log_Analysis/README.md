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

User: admin | IP: 192.168.1.10 | Status: Failed Login

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

findstr "Failed" sample_logs.txt

### Result

Filtered failed login attempts from log file.

### Conclusion

Multiple failed login attempts detected, indicating possible suspicious activity.
