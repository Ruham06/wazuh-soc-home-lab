# PowerShell Activity Detection with Wazuh

## Overview

PowerShell is widely used by Windows administrators, but attackers can also abuse it to execute malicious commands.

In this SOC home lab, Windows PowerShell activity is monitored using Wazuh and Windows security telemetry.

---

## Detection Goals

The objective is to identify suspicious PowerShell activity such as:

- Encoded PowerShell commands
- Suspicious command-line arguments
- PowerShell downloading files
- PowerShell executing scripts
- PowerShell launched by unusual processes
- Repeated suspicious PowerShell activity

---

## Data Flow

Windows Endpoint  
↓  
PowerShell Logging / Sysmon  
↓  
Windows Event Logs  
↓  
Wazuh Agent  
↓  
Wazuh Manager  
↓  
Detection Rules  
↓  
Wazuh Dashboard

---

## Important Indicators

Examples of suspicious PowerShell activity include:

- powershell.exe
- pwsh.exe
- -EncodedCommand
- -ExecutionPolicy Bypass
- DownloadString
- Invoke-WebRequest
- Invoke-Expression
- IEX

These indicators do not automatically mean an attack occurred, but they should be investigated.

---

## Investigation Process

When a suspicious PowerShell alert appears:

1. Review the alert in Wazuh.
2. Identify the affected endpoint.
3. Check the user account.
4. Review the PowerShell command line.
5. Identify the parent process.
6. Check related Sysmon events.
7. Review network connections.
8. Search for related alerts.
9. Map the activity to MITRE ATT&CK.
10. Determine whether the activity is legitimate or malicious.

---

## MITRE ATT&CK

Suspicious PowerShell execution can be associated with:

- Command and Scripting Interpreter
- PowerShell
- Execution
- Defense Evasion

Example technique:

T1059.001 - PowerShell

---

## Skills Demonstrated

- PowerShell monitoring
- Windows log analysis
- Wazuh alert investigation
- Endpoint threat detection
- Sysmon analysis
- Detection engineering
- MITRE ATT&CK mapping
