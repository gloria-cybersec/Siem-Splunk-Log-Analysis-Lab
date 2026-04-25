# SIEM Lab - Splunk Log Analysis & Brute Force Detection

## 🧠 Objective
Implement a SIEM lab using Splunk to ingest Windows Event Logs and detect failed login attempts (brute force activity).

---

## 🛠️ Tools Used
- Splunk Enterprise (SIEM)
- Windows 11 VM
- VMware Workstation

---

## 🧪 Scenario
A Windows machine was monitored using Splunk. Multiple failed login attempts were generated to simulate a brute force attack.

---

## ⚙️ Steps

### 1. Install Splunk
- Installed Splunk Enterprise on Windows VM
- Accessed via `http://localhost:8000`

### 2. Ingest Logs
- Added data using **Local Event Logs**
- Selected:
  - Security
  - System

### 3. Generate Events
- Locked system (`Win + L`)
- Entered incorrect password multiple times

### 4. Search Logs

Basic search:
```spl
index=*
