# Sysmon Detection with Wazuh

## Overview

Sysmon (System Monitor) provides detailed Windows endpoint telemetry that can be collected and analyzed by Wazuh.

In this SOC home lab, Sysmon telemetry is used to improve visibility into endpoint activity and support threat detection and investigation.

---

## Data Flow

Windows Endpoint  
↓  
Sysmon  
↓  
Windows Event Log  
↓  
Wazuh Agent  
↓  
Wazuh Manager  
↓  
Detection Rules  
↓  
Wazuh Dashboard

---

## Important Sysmon Events

### Event ID 1 - Process Creation

Records newly created processes.

Useful information includes:

- Process name
- Command line
- Parent process
- User
- Process ID
- File hash

This event is useful for detecting suspicious process execution.

---

### Event ID 3 - Network Connection

Records network connections initiated by processes.

Useful for identifying:

- Suspicious outbound connections
- Connections to unusual IP addresses
- Malware communication
- Command and Control activity

---

### Event ID 11 - File Creation

Records files created on the endpoint.

This can help identify:

- Suspicious executable files
- Malware downloads
- Scripts written to disk
- Unexpected files in sensitive directories

---

### Event ID 13 - Registry Modification

Records registry value modifications.

Registry monitoring is useful for detecting possible persistence mechanisms.

---

## PowerShell Monitoring

Sysmon process creation events can also help identify suspicious PowerShell execution.

Examples:

- powershell.exe
- pwsh.exe
- Encoded PowerShell commands
- Unusual command-line parameters
- PowerShell launched by unexpected applications

---

## SOC Investigation Example

When suspicious activity is detected:

1. Review the Wazuh alert.
2. Check the Sysmon Event ID.
3. Identify the process name.
4. Review the command line.
5. Check the parent process.
6. Identify the user account.
7. Review related network activity.
8. Check file hashes if available.
9. Map the activity to MITRE ATT&CK.
10. Determine whether the activity is legitimate or malicious.

---

## MITRE ATT&CK Examples

Sysmon telemetry can help detect activities related to:

- Execution
- Persistence
- Privilege Escalation
- Defense Evasion
- Discovery
- Command and Control

---

## Skills Demonstrated

- Endpoint monitoring
- Windows telemetry analysis
- Sysmon log analysis
- Wazuh alert investigation
- Detection engineering
- Threat hunting
- MITRE ATT&CK mapping
