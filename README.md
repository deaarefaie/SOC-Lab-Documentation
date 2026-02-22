# SOC Lab – Security Operations & SIEM Portfolio

## Overview
This repository documents a hands-on SOC (Security Operations Center) lab built to demonstrate practical skills in log analysis, detection engineering, alerting, correlation, and incident response using Splunk.

The lab simulates real-world SOC workflows, focusing on Windows endpoint monitoring, authentication attacks, suspicious process execution, and correlated attack detection.

## Lab Environment
- Operating System: Windows 10 (VMware)
- SIEM: Splunk Enterprise
- Log Sources:
  - Windows Security Event Logs
  - Sysmon (Process Creation, Network Connections)
- Tools:
  - Splunk Universal Forwarder
  - Sysmon

## Key Skills Demonstrated
- SIEM log ingestion and normalization
- Windows security event analysis
- Sysmon-based endpoint visibility
- Detection logic development using SPL
- Correlation rule creation
- Alert configuration and tuning
- SOC dashboard design
- Incident documentation and reporting

## Documented Incidents

### INC-001 – Suspicious PowerShell Execution
- Detection of encoded PowerShell commands using Sysmon Event ID 1
- Analysis of command-line activity and parent processes

### INC-002 – Brute Force Login Attempts
- Detection of repeated failed login attempts (Event ID 4625)
- Identification of targeted accounts and hosts

### INC-003 – Suspicious Network Activity
- Monitoring outbound network connections using Sysmon Event ID 3
- Identification of potentially abnormal communication patterns

### INC-004 – Correlated Brute Force and Post-Exploitation
- Correlation of:
  - Failed logins (4625)
  - Successful login (4624)
  - Suspicious PowerShell execution (Sysmon)
- Implemented as a scheduled Splunk alert
- Demonstrates reduction of false positives through event correlation

## SOC Alert Dashboard
A centralized SOC dashboard was created to aggregate detections and correlation alerts, providing:
- High-level visibility into security incidents
- Host-based impact assessment
- Analyst-ready investigation views

See: `SOC-Dashboard.md`

## Project Structure
