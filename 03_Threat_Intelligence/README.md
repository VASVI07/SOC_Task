# Threat Intelligence

# Objective

The objective of threat intelligence is to collect, process, analyze, and use information about cyber threats so that organizations can identify malicious activity early, understand attacker behavior, and take preventive action before damage occurs.
---

1. What is Threat Intelligence?
   
Threat intelligence is evidence-based knowledge about existing or emerging cyber threats. It includes contextual information about adversaries, their infrastructure, tools, indicators, motives, and tactics. Unlike raw alerts, threat intelligence adds meaning by explaining what the threat is, how it operates, and why it matters to the organization.

Key goals
  - Detect malicious domains, IP addresses, URLs, and file hashes before they are used successfully.
  - Understand attacker tactics, techniques, and procedures (TTPs).
  - Support incident response, vulnerability management, and security monitoring.
  - Reduce false positives by adding context to security alerts.

2. Types of Threat Intelligence

<img width="675" height="212" alt="image" src="https://github.com/user-attachments/assets/02bd18e0-09a0-4d74-8f7d-880c8a4a0d43" />


3. Threat Intelligence Lifecycle
   
A structured lifecycle helps convert raw data into actionable intelligence. The figure below summarizes the standard threat intelligence lifecycle used in many SOC and CTI workflows.

<img width="1020" height="376" alt="image" src="https://github.com/user-attachments/assets/06c6e0d1-a74a-44a1-bbd6-34aa03f93eed" />

- Planning: Define intelligence requirements such as phishing detection, ransomware monitoring, or third-party risk.
- Collection: Gather data from logs, endpoint alerts, email gateways, firewalls, open-source feeds, and dark web monitoring.
- Processing: Normalize data, deduplicate records, enrich IPs/domains/hashes, and convert raw feeds into usable formats.
- Analysis: Correlate indicators, identify patterns, map TTPs, assess risk, and estimate impact.
- Dissemination: Share findings with SOC analysts, management, incident responders, and other stakeholders.
- Feedback: Review what was useful, refine collection priorities, and improve future intelligence cycles.


4. Sources of Threat Intelligence
   
- Internal sources - SIEM alerts, firewall logs, DNS logs, endpoint detections, email security events, IDS/IPS logs, incident tickets.
- External sources - open-source intelligence (OSINT), commercial threat feeds, CERT advisories, vendor reports, and ISAC bulletins.
- Community sharing - MISP communities, AlienVault OTX, AbuseIPDB, security blogs, and malware sandboxes.
- Contextual enrichment - WHOIS records, passive DNS, geolocation, reputation databases, and MITRE ATT&CK references.

5. Indicators of Compromise (IOCs)
   
Indicators of Compromise are observable artifacts that may suggest malicious activity. Typical IOCs include suspicious IP addresses, domains, URLs, file hashes, email senders, registry keys, and unusual process names.

<img width="683" height="284" alt="image" src="https://github.com/user-attachments/assets/0bd47e7e-b253-475a-b76c-af707b049ec6" />

<img width="945" height="525" alt="image" src="https://github.com/user-attachments/assets/17514886-254a-4d65-8621-3d79034eb674" />


6. Tactics, Techniques, and Procedures (TTPs)
TTPs describe how attackers operate. They are more stable than individual IOCs and therefore more valuable for long-term defense. Many teams map observed activity to the MITRE ATT&CK framework.

<img width="671" height="254" alt="image" src="https://github.com/user-attachments/assets/6d54097d-2f6a-47f9-a3ac-4a064908f0bd" />

<img width="915" height="508" alt="image" src="https://github.com/user-attachments/assets/10f1b312-81c7-4e7c-9a7e-f0e3136391bf" />

7. Tools Used in Threat Intelligence (Conceptual)

   <img width="675" height="296" alt="image" src="https://github.com/user-attachments/assets/8892ea37-d7f9-4d0a-b6c9-7b5542a97b55" />

8. Practical Analysis Workflow
    
- Collect logs and indicators from email, firewall, DNS, proxy, endpoint, and authentication systems.
- Identify suspicious artifacts such as rare IPs, newly registered domains, unusual user-agent strings, or hash matches.
- Enrich indicators using reputation services and internal threat history.
- Correlate multiple events to see whether they belong to one campaign or intrusion path.
- Map findings to TTPs and estimate risk, impact, and likely objective of the attacker.
- Publish a concise intelligence summary with recommended containment and monitoring actions.

9. Sample Threat Intelligence Case Study
   
Scenario: The security team receives multiple alerts for a payroll-themed email. Several users clicked a link, one host connected to a rare external IP, and an unknown executable hash was detected on an endpoint.

<img width="676" height="228" alt="image" src="https://github.com/user-attachments/assets/4a7ee0cb-b5b6-41cb-83b9-c9fe03bf7159" />

10. Example Splunk Queries
    
- index=security sourcetype=proxy "*payroll*" OR "*login*" | stats count by src_ip, url, user
- index=security src_ip="185.220.101.45" OR dest_ip="185.220.101.45"
- index=edr hash="44d88612fea8a8f36de82e1278abb02f" | table _time host user process_name hash
- index=email subject="*Urgent Payroll Update*" | stats count by sender, recipient, subject
- index=dns query="*secure-check*" | stats count by src_ip, query, answer

11. Assessment: Normal or Suspicious?
    
Based on the indicators, contextual enrichment, and correlated behavior in the case study, the activity should be classified as suspicious. A single indicator may not be conclusive, but a combination of phishing email delivery, rare domain registration, malicious hash match, and periodic outbound beaconing provides strong evidence of malicious intent.

<img width="673" height="227" alt="image" src="https://github.com/user-attachments/assets/c9247cde-be88-4012-a20a-91042608fbd1" />

12. Recommendations
    
- Maintain updated IOC blocklists for IPs, domains, URLs, and hashes.
- Use SIEM correlation rules to connect email, DNS, proxy, and endpoint events.
- Apply multi-factor authentication and least privilege to reduce impact of credential theft.
- Train users to identify phishing emails and suspicious links.
- Subscribe to trusted threat feeds and regularly validate feed quality.
- Map detections to MITRE ATT&CK to improve visibility across the attack chain.

13. Outcome
    
Threat intelligence enables an organization to decide whether observed activity is normal or suspicious by combining indicators with context. In this assignment, the analyzed evidence shows how cyber intelligence transforms raw security events into actionable decisions such as blocking indicators, isolating hosts, warning users, and improving monitoring coverage.









