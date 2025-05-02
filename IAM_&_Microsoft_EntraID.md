# 🛡️ Identity and Access Management (IAM) & Microsoft Entra ID

## 🔐 What is IAM?

Identity and Access Management (IAM) is the framework of policies, technologies, and processes that ensure the right individuals access the right resources at the right times for the right reasons.

### Core Objectives

* **Authentication** – Verifying the identity of users/systems
* **Authorization** – Granting or denying access based on roles/policies
* **User Lifecycle Management** – Provisioning, modifying, de-provisioning
* **Access Governance** – Compliance, auditing, and policy enforcement

---

## 🔍 IAM Concepts

| Concept                  | Description                                                       |
| ------------------------ | ----------------------------------------------------------------- |
| Identity                 | A unique representation of a user/system                          |
| Principal                | Entity performing actions (user, app, device)                     |
| Authentication           | Proving identity via password, MFA, biometrics                    |
| Authorization            | Granting permissions based on roles or policies                   |
| RBAC (Role-Based Access) | Access decisions based on assigned roles                          |
| ABAC (Attribute-Based)   | Access decisions based on attributes (e.g., department, location) |
| Least Privilege          | Users get only the access they need                               |
| Separation of Duties     | No single entity has complete control or power                    |

---

## 🔐 Microsoft Entra ID (Azure AD)

Microsoft Entra ID (formerly Azure AD) is Microsoft's cloud-based identity and access management solution.

### ✨ Key Features

* **SSO (Single Sign-On)** for 1000s of SaaS apps
* **Conditional Access** for adaptive policy enforcement
* **Identity Protection** – Risk-based policies
* **Privileged Identity Management (PIM)** – Just-in-time elevation
* **Access Reviews & Governance**
* **Entitlement Management & Lifecycle Automation**

### 🧰 Core Components

| Component              | Purpose                                                                   |
| ---------------------- | ------------------------------------------------------------------------- |
| Entra ID               | Central identity service for Azure and M365                               |
| Entra ID Governance    | IGA (identity governance and admin) features                              |
| Conditional Access     | Policy engine to allow/block based on conditions (device, location, risk) |
| Entra PIM              | Elevation for privileged roles like Owner, Global Admin                   |
| Federation (SAML/OIDC) | Enables SSO across domains                                                |

### 🔐 Security Controls

* Enable **MFA** (Microsoft Authenticator, FIDO2)
* Use **Conditional Access** for location-based or risk-based access
* Configure **Access Reviews** for group and app access
* Implement **Just-in-Time (JIT)** access via **PIM**
* Enforce **SSPR** (Self-Service Password Reset) with registration

---

## 🔄 Integration & Federation

* Entra ID can federate with:

  * **On-Prem AD** (via Azure AD Connect)
  * **Third-party IdPs** (Ping, Okta, etc.) via SAML or OIDC
  * **Cloud apps** using SCIM for provisioning

---

## 🛠️ Tools & Commands

* **Azure Portal**: GUI for IAM configuration
* **Azure CLI / PowerShell**: Scripting for automation
* **Microsoft Graph API**: Programmatic access

---

## 💡 Best Practices

* Enforce **Zero Trust** – Always verify, assume breach
* Use **Conditional Access** to reduce risk exposure
* Monitor with **Microsoft Defender for Identity**
* Audit with **Azure AD Sign-In & Audit Logs**
* Regularly run **Access Reviews**
* Use **Privileged Identity Management** for admin roles

---

## 📘 Resources

* [Microsoft Entra Documentation](https://learn.microsoft.com/en-us/entra/)
* [Identity Architecture Guides](https://learn.microsoft.com/en-us/security/zero-trust/identity-overview)
* [MS Learn – Identity Path](https://learn.microsoft.com/en-us/training/paths/secure-your-cloud-data-azure/)
* [Zero Trust Identity Whitepaper](https://aka.ms/zerotrust)
