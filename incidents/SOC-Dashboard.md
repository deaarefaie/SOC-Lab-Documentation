# SOC Alert Dashboard

## Overview
This dashboard provides a centralized view of security alerts detected in a SOC lab environment.
It consolidates multiple detections and correlation rules into a single interface to support efficient monitoring and investigation.

## Objectives
- Provide high-level visibility into security events
- Highlight correlated attack patterns
- Support rapid triage and investigation by SOC analysts

## Dashboard Panels

### 1. Correlation Alert – Brute Force + Post-Exploitation
This panel detects correlated activity where:
- Multiple failed login attempts (Event ID 4625)
- Are followed by a successful login (Event ID 4624)
- And suspicious PowerShell execution (Sysmon Event ID 1)

**Purpose:**  
Reduce false positives by requiring multiple related indicators before triggering an alert.

### 2. Suspicious PowerShell Execution
Displays detailed information about PowerShell processes observed on monitored endpoints, including:
- Execution time
- Host
- User
- Command line
- Parent process

**Purpose:**  
Enable quick investigation of potentially malicious script execution.

## Data Sources
- Windows Security Event Logs
- Sysmon (Process Creation and Network Events)

## Use Case
This dashboard simulates a real-world SOC monitoring scenario where analysts:
- Identify suspicious authentication behavior
- Validate post-authentication activity
- Prioritize incidents based on correlated signals

## Screenshots

### Dashboard Overview
![SOC Dashboard Overview](screenshots/SOC-dashboard-overview.png)


## Conclusion
The SOC Alert Dashboard demonstrates the effective use of Splunk for:
- Security event correlation
- Alert visualization
- SOC-level monitoring workflows

This dashboard reflects common practices used in enterprise Security Operations Centers.
