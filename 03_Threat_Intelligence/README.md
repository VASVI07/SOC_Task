# Threat Intelligence

## Objective

To investigate IP addresses and determine whether they are malicious or safe using threat intelligence tools.

---

## Tools Used

- VirusTotal  
- AbuseIPDB  

---

## Investigation 1: Suspicious IP

### IP Address
185.220.101.1  

### Analysis

- Checked the IP on VirusTotal  
- Multiple security vendors flagged the IP as suspicious  
- Associated with malicious or anonymized traffic  

- Checked on AbuseIPDB  
- Reports indicate abusive or suspicious behavior  
- High confidence of abuse  

### Conclusion

This IP is potentially malicious and may be linked to suspicious network activity.  
Such IPs should be monitored or blocked in a real SOC environment.

---

## Investigation 2: Clean IP

### IP Address
8.8.8.8  

### Analysis

- Checked the IP on VirusTotal  
- No malicious detections  

- Checked on AbuseIPDB  
- IP belongs to Google Public DNS  
- Trusted and widely used  

### Conclusion

This IP is safe and represents normal network activity.

---

## Screenshot Evidence

### VirusTotal Result



### AbuseIPDB Result

![AbuseIPDB](../08_Screenshots/threat_abuse.png)
