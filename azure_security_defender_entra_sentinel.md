# ☁️ Microsoft Azure Security

A focused summary of security tools and services in Azure for managing identity, securing workloads, and maintaining visibility and control.

---

## 🔐 1. Azure Security Overview

Azure provides a shared responsibility model. While Microsoft manages the physical infrastructure, you must secure identities, data, networks, and workloads within your Azure environment.

---

## 🛡️ 2. Microsoft Defender for Cloud

### What It Is:
A Cloud Security Posture Management (CSPM) and Workload Protection Platform (CWPP).

### Key Features:
- Continuous assessment of Azure resources
- Security recommendations
- Regulatory compliance dashboard (e.g., NIST, ISO 27001)
- Integration with Microsoft Sentinel
- Defender plans for Servers, SQL, Containers, Key Vault, etc.

### Use Case:
Automatically alerts if a virtual machine is exposed to the internet with weak credentials.

---

## 👥 3. Microsoft Entra ID (formerly Azure AD)

### What It Is:
Identity and Access Management (IAM) service enabling SSO, MFA, conditional access, and identity protection.

### Key Services:
- **SSO:** Single sign-on for SaaS apps
- **Conditional Access:** Enforces policies based on device, location, risk
- **Identity Protection:** Detects sign-in risks (impossible travel, etc.)
- **Governance (IGA):** Access reviews, entitlement management, PIM
- **B2B/B2C:** Federated identity for partners/customers

### Use Case:
Enforce MFA and block access from unknown countries for sensitive applications.

---

## 🧠 4. Microsoft Sentinel

### What It Is:
A cloud-native SIEM and SOAR solution for intelligent threat detection, investigation, and automated response.

### Core Capabilities:
- Collect logs from Microsoft 365, Azure, AWS, Firewalls
- Use Kusto Query Language (KQL) for threat hunting
- Detect anomalies using ML-based analytics rules
- Create automated playbooks with Logic Apps

### Use Case:
Sentinel detects suspicious RDP brute-force attempts on VMs, correlates with Azure AD sign-in logs, and triggers a playbook to disable the account and notify security.

---

## 🔄 Integration Example:

| Component          | Function                                   |
|--------------------|--------------------------------------------|
| Defender for Cloud | Identifies vulnerabilities and misconfigs  |
| Entra ID           | Applies access controls & MFA              |
| Sentinel           | Correlates alerts, automates incident response |

---

## 🧪 Lab Practice Ideas:
- Enable Defender for Cloud and check recommendations.
- Create and enforce Conditional Access policies in Entra ID.
- Integrate Microsoft 365 logs into Sentinel and create detection rules.

---

## 📚 References:
- [Microsoft Defender for Cloud Docs](https://learn.microsoft.com/en-us/azure/defender-for-cloud/)
- [Entra ID (Azure AD) Docs](https://learn.microsoft.com/en-us/azure/active-directory/)
- [Microsoft Sentinel Docs](https://learn.microsoft.com/en-us/azure/sentinel/)
