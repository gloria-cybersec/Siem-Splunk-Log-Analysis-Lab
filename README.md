# SIEM Lab - Splunk Log Analysis

## Objective
Detect failed login attempts using Splunk and Windows logs.

---

## Tools
- Splunk Enterprise
- Windows 11 VM
- VMware

---

## What I did

1. Installed Splunk
2. Added Windows Event Logs (Security, System)
3. Generated failed logins (wrong password)
4. Searched logs in Splunk

---

## Detection

Failed logins:

```spl
EventCode=4625

Analysis:

EventCode=4625 | stats count by Account_Name, host

Detailed:
EventCode=4625 | table _time Account_Name host Source_Network_Address Logon_Type

Results
Detected failed login attempts
Users affected: CYBERLAB$, Labuser
Source: 127.0.0.1 (local machine)
Screenshots
