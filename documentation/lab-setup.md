# Wazuh SOC Home Lab Setup

## Overview

This document describes the setup of my Wazuh-based SOC home lab.

The purpose of this lab is to gain practical experience with:

- Centralized security monitoring
- Endpoint telemetry collection
- Windows security event analysis
- Sysmon monitoring
- File Integrity Monitoring
- Detection engineering
- Threat hunting
- MITRE ATT&CK mapping
- Security alert investigation

---

# Lab Architecture

The basic data flow of the lab is:

Windows Endpoint  
↓  
Wazuh Agent  
↓  
Wazuh Manager  
↓  
Wazuh Detection Engine  
↓  
Wazuh Dashboard  
↓  
SOC Analyst Investigation

The Windows endpoint generates security telemetry which is collected by the Wazuh Agent and forwarded to the Wazuh Manager for analysis.

---

# Lab Components

The lab environment includes:

- Wazuh Manager
- Wazuh Dashboard
- Wazuh Indexer
- Windows Endpoint
- Wazuh Windows Agent
- Sysmon
- Windows Event Logs
- Windows Defender
- PowerShell Logging

---

# Step 1 – Install Wazuh Manager

The Wazuh server was configured to centrally collect and analyze security events from monitored endpoints.

Example installation command:

```bash
curl -sO https://packages.wazuh.com/4.x/wazuh-install.sh
sudo bash ./wazuh-install.sh -a
