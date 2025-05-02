# ☁️ Google Cloud Security Fundamentals

## 🔐 Overview
Google Cloud Platform (GCP) provides built-in security services to protect data, applications, and infrastructure. Understanding key GCP security features helps secure cloud workloads.

---

## 🧱 Core GCP Security Concepts

| Concept | Description |
|--------|-------------|
| IAM (Identity and Access Management) | Define who (identity) has what access (roles/permissions) to which GCP resources. |
| VPC Service Controls | Establish a security perimeter around GCP services to mitigate data exfiltration risks. |
| Cloud Audit Logs | Track user and system activity on GCP resources for compliance and incident response. |
| Cloud Identity | Centralized identity management platform for users and groups. Integrated with Google Workspace. |
| KMS (Key Management Service) | Create, use, rotate, and manage cryptographic keys. Supports CMEK (Customer Managed Encryption Keys). |
| Confidential Computing | Keeps data encrypted in memory and during processing using secure enclaves. |
| Shielded VMs | Hardened virtual machines with secure boot and integrity monitoring. |
| Binary Authorization | Prevents the deployment of untrusted containers by enforcing image signing policies. |

---

## 🛡️ GCP IAM Best Practices

- Follow principle of least privilege: assign minimum permissions required.
- Use predefined roles when possible instead of primitive roles (Owner, Editor, Viewer).
- Enable 2-Step Verification and context-aware access.
- Use service accounts for applications and automation — restrict their scopes.
- Use Cloud Identity Groups for managing user access at scale.

---

## 🧪 Logging, Monitoring & Threat Detection

| Tool | Purpose |
|------|---------|
| Cloud Logging | Aggregates logs from GCP services and applications. |
| Cloud Monitoring | Visualizes metrics, sets up dashboards, and sends alerts. |
| Cloud Audit Logs | Admin Activity, Data Access, and System Events logging. |
| Security Command Center | Centralized visibility into misconfigurations, vulnerabilities, and threats. |
| Event Threat Detection | Real-time threat detection based on log analysis and threat intelligence. |

---

## 🔐 Encryption

- **Default Encryption:** All data is encrypted at rest and in transit by default.
- **Customer Managed Encryption Keys (CMEK):** For compliance and enhanced control.
- **Customer Supplied Encryption Keys (CSEK):** You bring your own encryption keys.
- **Envelope Encryption:** Encrypts data with a data encryption key (DEK), which is itself encrypted with a key encryption key (KEK).

---

## 🧪 Hands-On Practice Ideas

1. Create IAM roles and policies.
2. Use Cloud KMS to encrypt/decrypt files.
3. Explore Security Command Center in a GCP project.
4. Set up alerting for IAM changes using Cloud Monitoring.
5. Create a VPC Service Control perimeter around sensitive services.

---

## 📚 References
- [Google Cloud IAM Documentation](https://cloud.google.com/iam/docs)
- [Security Command Center](https://cloud.google.com/security-command-center)
- [GCP Best Practices Center](https://cloud.google.com/docs/security/best-practices)
- [Binary Authorization](https://cloud.google.com/binary-authorization)

---

> ✅ **Tip:** Always monitor the Google Cloud release notes and security bulletins to stay up to date on new features and patches.
