# Capstone Project - SOC Investigation Report

## Incident Summary

A suspicious login pattern was detected involving multiple failed login attempts followed by a successful login.

## Investigation Steps

1. Analyzed login logs
2. Identified repeated failed attempts
3. Checked IP address (192.168.1.10)
4. Determined IP is private (internal network)
5. Performed alert triage
6. Escalated incident

## Findings

* Multiple failed login attempts observed
* Same IP used repeatedly
* Successful login after failures
* Activity originated from internal network

## Risk Assessment

Medium risk due to suspicious login behavior.

## Actions Taken

* Documented logs and findings
* Escalated to senior team
* Recommended monitoring

## Recommendations

* Implement account lockout policy
* Monitor login attempts
* Review user activity logs

## Conclusion

The activity is suspicious but not confirmed as an attack. Further monitoring is required.
## Executive Summary

This report presents the analysis of a suspicious login activity detected through log monitoring. Multiple failed login attempts followed by a successful login were observed. Threat intelligence analysis indicated the IP was not malicious. The activity was classified as suspicious and escalated for further investigation.
