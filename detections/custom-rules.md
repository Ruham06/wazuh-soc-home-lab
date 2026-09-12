# Wazuh Custom Detection Rules

## Overview

This section documents detection engineering work performed in the Wazuh SOC Home Lab.

The goal is to detect suspicious endpoint activity using Windows Event Logs, Sysmon telemetry, PowerShell logs, Windows Defender alerts, and Wazuh detection rules.

---

## Detection Sources

The following telemetry sources were used:

- Windows Security Event Logs
- Sysmon
- PowerShell Logs
- Windows Defender
- Wazuh Agent
- Wazuh Detection Engine

---

## Detection Workflow

The detection process follows this flow:

Windows Endpoint  
↓  
Security Event / Sysmon Event  
↓  
Wazuh Agent  
↓  
Wazuh Manager  
↓  
Decoder and Detection Rule  
↓  
Security Alert  
↓  
SOC Investigation

---

## Detection Use Cases

### 1. Suspicious PowerShell Activity

PowerShell activity can be monitored to identify suspicious commands or unusual execution behavior.

Examples of suspicious activity include:

- Encoded PowerShell commands
- Execution of downloaded scripts
- Unusual PowerShell processes
- PowerShell commands executed from unexpected applications

Telemetry Source:

- PowerShell Event Logs
- Sysmon Process Creation Events

---

### 2. Failed Login Detection

Windows authentication events can be monitored to identify repeated failed login attempts.

Possible indicators:

- Multiple failed logins
- Repeated authentication failures from the same source
- Login attempts against multiple accounts

This type of detection can help identify possible brute-force attacks.

---

### 3. Windows Defender Alerts

Windows Defender security events can be forwarded to Wazuh.

Wazuh can then analyze these events and generate alerts when malicious or suspicious files are detected.

---

### 4. Sysmon Process Monitoring

Sysmon provides detailed endpoint telemetry.

Important events include:

- Process creation
- Network connections
- File creation
- Registry modifications
- PowerShell execution

These events provide additional context during SOC investigations.

---

## MITRE ATT&CK Mapping

Detection alerts can be mapped to MITRE ATT&CK techniques to understand attacker behavior.

Example categories:

- Execution
- Persistence
- Credential Access
- Discovery
- Command and Control

MITRE ATT&CK mapping helps SOC analysts understand the attack stage associated with an alert.

---

## Investigation Process

When Wazuh generates an alert, the investigation process includes:

1. Review alert severity.
2. Identify the affected endpoint.
3. Review the triggering event.
4. Check process and user information.
5. Review related Sysmon or Windows events.
6. Map suspicious activity to MITRE ATT&CK.
7. Determine whether the alert is malicious or a false positive.
8. Document investigation findings.

---

## Future Detection Improvements

Future improvements include:

- SSH brute-force detection
- RDP brute-force detection
- Automated IP blocking
- Active Response
- Malware detection using YARA
- Threat intelligence integration
- Automated endpoint isolation
