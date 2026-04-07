# Capstone Project – SOC Investigation

## Objective

The objective of this project is to simulate a real-world Security Operations Center (SOC) investigation by analyzing suspicious login activity, validating threats using external intelligence sources, and documenting the findings.

---

## Scenario

During routine monitoring, multiple failed login attempts were detected on a Windows system. The frequency and pattern of these attempts suggested potential unauthorized access or brute force activity.

---

## Step 1: Log Analysis

Windows Security Event Logs were analyzed, focusing on Event ID **4625**, which represents failed login attempts.

### Observations

- Multiple failed login attempts were recorded
- Attempts occurred within a short time frame
- Repeated login failures indicate abnormal behavior
- Pattern suggests possible brute force attempt

---

## Step 2: Command Line Investigation

To filter relevant events, the following command was used:


### Result

The command extracted all failed login entries from the exported log file, allowing focused analysis of suspicious activity.

---

## Step 3: Threat Intelligence Analysis

The suspicious IP address identified from logs was analyzed using external threat intelligence platforms.

### Tools Used

- VirusTotal  
- AbuseIPDB  

### Findings

- VirusTotal reported **14 out of 94 security vendors flagged the IP as malicious**
- AbuseIPDB showed **100% abuse confidence score**
- The IP was identified as a **TOR exit node**, often associated with anonymized and potentially malicious activity

---

## Step 4: Analysis

- Continuous failed login attempts indicate an attempt to gain unauthorized access
- The use of a flagged IP address strengthens suspicion
- Threat intelligence confirms the IP has a malicious reputation
- The activity is not consistent with normal user behavior

---

## Step 5: Conclusion

Based on log analysis and threat intelligence findings, the activity is highly suspicious and likely represents a brute force attack attempt originating from a malicious source.

---

## Step 6: Actions Taken

- Suspicious activity was documented  
- Alert was triaged and categorized as Medium severity  
- Evidence (log files) was preserved for further investigation  
- Recommendation made to monitor activity and block the IP if necessary  

---

