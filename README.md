# Wazuh-Based SOC Home Lab
## Detection, Threat Hunting and Endpoint Monitoring

### Overview
This project demonstrates a small Security Operations Center (SOC) home lab built using Wazuh.

The goal of the project is to gain hands-on experience with centralized security monitoring, endpoint telemetry, detection engineering, threat hunting, and security event investigation.

---

## Lab Environment

- Wazuh Manager
- Windows Endpoint
- Wazuh Agent
- Windows Event Logs
- Windows Defender
- Sysmon
- PowerShell Logging

---

## Security Technologies

- Wazuh SIEM/XDR
- Sysmon
- MITRE ATT&CK
- Windows Defender
- File Integrity Monitoring (FIM)
- Custom Wazuh Rules
- PowerShell Monitoring
- YARA
- VirusTotal Integration
- Security Configuration Assessment (SCA)
- Suricata IDS

---

## Architecture

Windows Endpoint  
↓  
Wazuh Agent  
↓  
Wazuh Manager  
↓  
Detection Rules / Correlation  
↓  
Wazuh Dashboard  
↓  
SOC Analyst Investigation

---

## Activities Performed

1. Installed and configured a Wazuh SOC environment.
2. Connected a Windows endpoint with the Wazuh Manager.
3. Collected Windows Security Event Logs.
4. Integrated Sysmon telemetry.
5. Enabled File Integrity Monitoring.
6. Monitored Windows Defender events.
7. Created and tested custom Wazuh detection rules.
8. Monitored PowerShell activities.
9. Mapped security events to MITRE ATT&CK techniques.
10. Performed controlled attack simulations.
11. Investigated security alerts using the Wazuh Dashboard.
12. Practiced threat hunting using endpoint telemetry.

---

## Detection and Threat Hunting

The lab was used to investigate activities such as:

- Failed login attempts
- Suspicious PowerShell activity
- File modifications
- Windows security events
- Malware-related indicators
- Suspicious process execution
- MITRE ATT&CK mapped activities

---

## Tools Used

| Tool | Purpose |
|---|---|
| Wazuh | SIEM/XDR, alerting and endpoint monitoring |
| Sysmon | Detailed Windows endpoint telemetry |
| Windows Defender | Malware detection |
| MITRE ATT&CK | Mapping attacker techniques |
| PowerShell Logging | Command and script monitoring |
| YARA | Malware pattern detection |
| VirusTotal | IOC and file reputation analysis |
| Suricata | Network IDS monitoring |

---

## Skills Demonstrated

- SOC Monitoring
- SIEM Administration
- Alert Investigation
- Detection Engineering
- Threat Hunting
- Endpoint Security Monitoring
- Log Analysis
- MITRE ATT&CK Mapping
- Incident Investigation
- Windows Security Monitoring

---

## Future Improvements

- Wazuh Active Response
- Automated endpoint isolation
- SSH/RDP brute-force blocking
- Automated incident response
- Cloud monitoring
- Threat intelligence integration
- Advanced dashboards
- Security automation

---

## Disclaimer

All testing in this project was performed in a controlled lab environment for educational and defensive cybersecurity purposes.
