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
