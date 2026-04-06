# Final SOC Investigation Report

## Executive Summary

A suspicious login activity was detected involving multiple failed login attempts followed by a successful login. The activity was analyzed using log analysis and threat intelligence tools. The IP was found to be internal and not malicious. The activity was classified as suspicious and escalated for further monitoring.

## Incident Description

Logs showed repeated failed login attempts for a user account from the same IP address, followed by a successful login.

## Log Analysis

* Multiple failed login attempts detected
* Same IP address used repeatedly
* Successful login after failures

## Threat Intelligence

* IP analyzed using VirusTotal and AbuseIPDB
* No malicious activity detected
* IP identified as internal/private or trusted

## Triage Decision

* Classified as suspicious activity
* Not confirmed as an attack

## Escalation

* Incident escalated to higher-level analysis due to unusual login pattern

## Evidence Collected

* Log file (sample_logs.txt)
* Command line output (findstr)
* Screenshots from VirusTotal and AbuseIPDB

## Tools Used

* Command Prompt (findstr)
* VirusTotal
* AbuseIPDB
* GitHub

## Recommendations

* Monitor user login activity
* Implement account lockout policy
* Review authentication logs regularly

## Conclusion

The activity is suspicious but not confirmed as malicious. Continuous monitoring is recommended to ensure system security.

