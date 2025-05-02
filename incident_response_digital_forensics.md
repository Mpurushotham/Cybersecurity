# 🛡️ Incident Response & Digital Forensics

## 📘 Overview

Incident Response (IR) and Digital Forensics (DFIR) are critical disciplines within cybersecurity. They focus on detecting, responding to, investigating, and recovering from security incidents, breaches, or threats.

---

## 🚨 Incident Response (IR)

### 🔍 What is Incident Response?
A structured approach for managing and mitigating the aftermath of a cybersecurity incident to limit damage and reduce recovery time and cost.

### 📋 Incident Response Lifecycle (NIST SP 800-61)
1. **Preparation** – Tools, training, communication plans, policies.
2. **Detection & Analysis** – Identify signs of potential incidents, logs, alerts.
3. **Containment, Eradication, Recovery** – Limit spread, remove cause, restore systems.
4. **Post-Incident Activity (Lessons Learned)** – Document, review, update processes.

### 🧰 Tools Used in IR
- SIEMs: Microsoft Sentinel, Splunk, QRadar
- EDR: Microsoft Defender for Endpoint, CrowdStrike, SentinelOne
- SOAR: Palo Alto Cortex XSOAR, IBM Resilient
- Ticketing: JIRA, ServiceNow

---

## 🔬 Digital Forensics

### 💡 What is Digital Forensics?
The science of collecting, preserving, analyzing, and presenting digital evidence in a legally acceptable manner.

### 🔍 Common Types of Digital Forensics
- **Disk Forensics** – Analyze hard drives, partitions.
- **Memory Forensics** – Live RAM analysis.
- **Network Forensics** – Analyze traffic captures (e.g., PCAP).
- **Mobile Forensics** – Recover data from mobile devices.
- **Cloud Forensics** – Investigate logs and artifacts from cloud platforms.

### 🧪 Tools Used in Digital Forensics
- Autopsy/Sleuth Kit
- FTK Imager
- Volatility (Memory analysis)
- Wireshark
- X-Ways Forensics
- Plaso (log2timeline)

---

## 📌 Key Concepts

| Concept | Description |
|--------|-------------|
| **Chain of Custody** | Documentation of evidence handling from collection to court. |
| **Forensically Sound** | Process does not alter original evidence. |
| **Time Stomping** | Tampering with file timestamps (anti-forensics technique). |
| **Indicator of Compromise (IOC)** | Artifacts observed on a system/network indicating intrusion. |
| **Root Cause Analysis (RCA)** | Method to identify the origin of the incident. |

---

## 🧭 Sample Incident Response Workflow

```text
🔹 Alert Received from SIEM
🔹 Initial Triage (false positive check)
🔹 Assign Incident Severity (Critical, High, Medium, Low)
🔹 Begin Containment (e.g., isolate host)
🔹 Investigate logs, behavior, forensics
🔹 Eradicate threat (patch, remove malware)
🔹 Recover system (restore backup, reimage)
🔹 Post-Incident Review & Documentation
