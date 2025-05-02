# 🛡️ Container Security (Docker & Kubernetes)

## 🚢 Docker Security

### 1. Docker Architecture Security
- **Daemon Security**: Run Docker daemon with least privilege. Avoid running it as root.
- **Namespaces & Cgroups**: Used for isolation and resource limiting.
- **Seccomp**: Restricts the system calls a container can make.

### 2. Docker Image Security
- Use **minimal base images** (e.g., Alpine).
- Scan images with tools like **Trivy**, **Clair**, or **Docker Scout**.
- Sign images with **Docker Content Trust (Notary)**.

### 3. Docker Container Runtime Security
- Avoid `--privileged` containers.
- Set user using `USER` directive in Dockerfile (avoid root).
- Use `read-only` file systems and drop unnecessary Linux capabilities.

### 4. Docker Host Security
- Harden the host OS.
- Restrict Docker socket access (`/var/run/docker.sock`).
- Monitor Docker logs and use auditd for tracking API calls.

## ☸️ Kubernetes Security

### 1. Cluster Setup & RBAC
- Enable **RBAC** (Role-Based Access Control).
- Restrict access to the **Kube API Server**.
- Disable anonymous access and restrict permissions via `ClusterRole` & `RoleBindings`.

### 2. Pod Security
- Enforce **Pod Security Standards** (Baseline, Restricted).
- Use **Pod Security Policies** (deprecated) or **OPA Gatekeeper/Kyverno**.
- Avoid running containers as root: `runAsNonRoot: true`.

### 3. Network Security
- Use **Network Policies** to restrict pod-to-pod traffic.
- Isolate namespaces using network segmentation.

### 4. Secrets Management
- Use **Kubernetes Secrets** encrypted at rest (KMS integration).
- Prefer external secrets managers: **Vault**, **AWS Secrets Manager**, **Azure Key Vault**.

### 5. Supply Chain Security
- Sign container images and validate them via **Sigstore**, **Cosign**, or **Notary v2**.
- Use admission controllers to enforce security policies (e.g., no unsigned images).

### 6. Monitoring and Logging
- Enable **audit logs** on the Kubernetes API server.
- Monitor with tools like **Falco**, **Sysdig**, **Prometheus/Grafana**.

## 🛠 Tools for Container Security
- **Trivy** – Vulnerability scanner for Docker/K8s.
- **Aqua Security** – End-to-end container security platform.
- **Anchore** – Scanning & policy enforcement.
- **Sysdig/Falco** – Runtime security monitoring.
- **Kube-bench** – CIS Kubernetes benchmark testing.

## ✅ Best Practices Summary
| Area | Best Practice |
|------|---------------|
| Dockerfile | Use minimal base images, avoid root, scan early |
| Runtime | Drop capabilities, avoid privileged mode |
| Secrets | Use external secret managers |
| K8s RBAC | Grant least privilege |
| Logging | Enable audit logging |
| Network | Use Network Policies |

---

