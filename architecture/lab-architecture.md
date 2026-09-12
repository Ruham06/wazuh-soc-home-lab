# Wazuh SOC Lab Architecture

## Data Flow

Windows Endpoint
→ Wazuh Agent
→ Wazuh Manager
→ Wazuh Detection Engine
→ Wazuh Dashboard
→ SOC Analyst

## Endpoint Telemetry

The Windows endpoint sends security telemetry including:

- Windows Event Logs
- Sysmon events
- File Integrity Monitoring events
- PowerShell activity
- Windows Defender alerts

The Wazuh Manager analyzes the collected telemetry using decoders and detection rules and generates security alerts for investigation.
