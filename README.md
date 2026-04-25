# SIEM Lab - Splunk Log Analysis & Brute Force Detection

## 🧠 Objective
Implement a SIEM lab using Splunk to ingest Windows Event Logs and detect failed login attempts (brute-force activity).

---

## 🛠️ Tools Used
- Splunk Enterprise (SIEM)
- Windows 11 Virtual Machine
- VMware Workstation

---

## 🧪 Scenario
A Windows machine was monitored using Splunk. Multiple failed login attempts were generated to simulate a brute-force attack against local user accounts.

---

## ⚙️ Steps

### 1. Install Splunk
- Installed Splunk Enterprise on a Windows VM
- Accessed the interface via:
  http://localhost:8000

---

### 2. Ingest Windows Logs
- Configured data input using:
  - Local Event Logs
- Selected:
  - Security
  - System

---

### 3. Simulate Attack
- Locked the system using `Win + L`
- Entered incorrect passwords multiple times
- Generated Windows Security Event ID 4625

---

### 4. Log Analysis

#### Basic Search
```spl
index=*

Failed Login Detection
EventCode=4625

Aggregated Analysis
EventCode=4625 | stats count by Account_Name, host

Detailed Event Analysis
EventCode=4625 | table _time Account_Name host Source_Network_Address Logon_Type

🔍 Results
Detected multiple failed login attempts (Event ID 4625)
Identified affected accounts:
CYBERLAB$
Labuser
Source of activity:
127.0.0.1 (local machine)
Logon type:
Type 2 (interactive login)

📸 Screenshots
Splunk Dashboard / Search Interface

Logs Successfully Ingested

Failed Login Detection (EventCode 4625)

Aggregated Analysis

Detailed Event Analysis

💡 Key Takeaways
Splunk successfully ingests and analyzes Windows Event Logs
Event ID 4625 is critical for detecting failed login attempts
Local attacks may not include external IP addresses
Log analysis can still identify attack patterns using:
Account names
Host
Logon type

💼 Resume Value

This lab demonstrates:

SIEM implementation and configuration
Log ingestion and parsing
Security event detection (brute-force attempts)
Basic threat investigation and analysis
Hands-on experience with real security data
