# ☸️ Kubernetes Security & DevSecOps

## Overview
Kubernetes is a powerful container orchestration platform. However, its complexity introduces unique security challenges. DevSecOps practices help integrate security from development through deployment in Kubernetes environments.

---

## 🔐 Kubernetes Security Concepts

### 1. **Pod Security**
- **Security Context**: Define privileges and access controls for pods.
- **PodSecurity Admission (PSA)**: Enforces security standards like `privileged`, `baseline`, `restricted`.

### 2. **RBAC (Role-Based Access Control)**
- Controls who can perform actions in the cluster.
- Resources:
  - `Role`, `ClusterRole`, `RoleBinding`, `ClusterRoleBinding`

### 3. **Network Policies**
- Restrict pod communication using namespaces and labels.
- Helps implement Zero Trust Networking.

### 4. **API Server Security**
- Secure access using authentication (OIDC, certificates).
- Encrypt secrets at rest.

### 5. **Image Security**
- Use signed and scanned images.
- Pin versions and avoid `:latest` tags.

---

## 🔄 DevSecOps in Kubernetes

### 1. **Secure CI/CD Pipelines**
- Integrate security scanners into pipeline stages.
- Prevent vulnerable images or misconfigured deployments.

### 2. **Policy-as-Code (OPA/Gatekeeper)**
- Use Rego policies to enforce rules (e.g., disallow privileged containers).

### 3. **Secret Management**
- Use tools like:
  - **HashiCorp Vault**
  - **Sealed Secrets**
  - **Kubernetes External Secrets**

### 4. **Runtime Security**
- Tools: Falco, Sysdig Secure
- Monitor system calls and detect anomalies.

### 5. **Admission Controllers**
- Validate and mutate resources before they are persisted.
- Examples: PodSecurityPolicy (deprecated), Kyverno, Gatekeeper

---

## 🔧 Tools
| Category | Tools |
|---------|-------|
| Image Scanning | Trivy, Clair, Anchore, Snyk |
| Secret Detection | GitLeaks, Spectral |
| Policy Enforcement | OPA, Kyverno, Gatekeeper |
| Monitoring | Prometheus, Grafana, Falco |
| CI/CD Security | Checkov, KubeSec, Kubeaudit |

---

## 🚨 Example DevSecOps Workflow
1. **Developer** commits code and Dockerfile.
2. **CI/CD** pipeline triggers image build.
3. **Image Scanner** checks for vulnerabilities.
4. **Kubernetes Linter** validates manifests.
5. **OPA/Gatekeeper** ensures compliance.
6. **Admission Controller** enforces policy.
7. **Runtime Monitoring** watches behavior in prod.

---

## 🔒 Best Practices
- Enable RBAC and audit logging.
- Enforce least privilege via roles and network policies.
- Use secrets management — don’t hardcode secrets.
- Restrict root and privileged containers.
- Regularly scan and patch containers and Kubernetes.

---

## 📚 References
- [Kubernetes Security Best Practices](https://kubernetes.io/docs/concepts/security/overview/)
- [CNCF Cloud Native Security Whitepaper](https://github.com/cncf/tag-security/blob/main/security-whitepaper/cloud-native-security-whitepaper.pdf)
- [OWASP Kubernetes Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Kubernetes_Security_Cheat_Sheet.html)
