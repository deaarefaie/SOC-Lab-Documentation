# INC-004 – DNS Query Activity Detected

## Date
2026-02-20

## Environment
- Operating System: Windows 10 (VMware)
- SIEM: Splunk Enterprise
- Log Source: Sysmon
- Event ID: 22 (DNS Query)

## Incident Description
A DNS query was detected from a local process.
Monitoring DNS queries is critical as attackers often use DNS for command-and-control communication.

## Detection Logic (Splunk Query)

```spl
index=win10_13_sysmon EventID=22
| table _time Image QueryName QueryResults User
```
Evidence

Event ID: 22

Process Image: PING.EXE

Query Name: google.com

Query Results: 142.251.127.138 (and others)

User: DESKTOP-A5RQE1G\deaar

Host: DESKTOP-A5RQE1G

## Screenshots

### Splunk Detection Query
![Splunk Search Result](../screenshots/INC-004-dns-query.png)

Analysis

DNS queries initiated by system utilities such as ping.exe are typically benign.
However, monitoring DNS activity is essential for detecting malicious domains, beaconing behavior, or DNS tunneling.
In this lab scenario, the activity was generated intentionally.

Severity

Low

Response Actions

DNS query reviewed

Domain verified as legitimate

No further action required

Continued DNS monitoring recommended

Conclusion

No malicious activity was identified.
This incident validates the ability to detect and analyze DNS queries using Sysmon Event ID 22 and Splunk.
