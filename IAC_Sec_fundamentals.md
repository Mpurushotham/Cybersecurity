# 🛠️ Infrastructure as Code (IaC) Security

Infrastructure as Code (IaC) allows the provisioning and management of infrastructure through code instead of manual processes. While it brings speed and scalability, it also introduces security risks if not properly managed.

---

## 📌 Why IaC Security Matters

* IaC templates define critical infrastructure (networks, firewalls, VMs, storage).
* Misconfigurations can lead to exposed data, open ports, or privilege escalation.
* IaC code is often stored in Git repositories – exposing secrets or vulnerable configurations.

---

## 🔍 Common IaC Security Risks

| Risk                    | Description                                                          |
| ----------------------- | -------------------------------------------------------------------- |
| Hardcoded secrets       | Credentials or API keys embedded directly in templates               |
| Open security groups    | Broad inbound rules (e.g., `0.0.0.0/0` on SSH/HTTP)                  |
| Insecure defaults       | Templates using weak settings by default (e.g., disabled encryption) |
| Lack of version control | Untracked changes or unauthorized edits to templates                 |
| Drift                   | Infrastructure that no longer matches the IaC definition             |

---

## 🛡️ Best Practices for IaC Security

### 🔐 Secure Secrets Management

* Never hardcode secrets in code.
* Use environment variables, secrets managers (Vault, AWS Secrets Manager, Azure Key Vault).

### 🔎 Code Scanning

* Use static analysis tools to detect misconfigurations and security issues:

  * **Checkov** (Terraform, CloudFormation)
  * **tfsec** (Terraform)
  * **KICS** (Infrastructure code scanning)
  * **cfn-nag** (CloudFormation)

### ✅ Least Privilege

* Follow the principle of least privilege when assigning IAM roles/policies.
* Regularly review permissions defined in your templates.

### 🔁 Version Control & CI/CD Integration

* Store IaC in Git repositories.
* Integrate security scanning into CI/CD pipelines (e.g., GitHub Actions, GitLab CI).

### 🧪 Testing and Validation

* Perform dry-runs (e.g., `terraform plan`, `pulumi preview`) before applying changes.
* Use policy-as-code tools (e.g., Open Policy Agent, Sentinel) to enforce governance.

### 🗃️ Modular Design

* Break templates into reusable modules for better control and review.
* Use official or community-vetted modules (with caution).

---

## 🧰 Tools for IaC Security

| Tool       | Description                                                             |
| ---------- | ----------------------------------------------------------------------- |
| Checkov    | Scans Terraform, CloudFormation, Kubernetes, etc. for misconfigurations |
| tfsec      | Static analysis for Terraform security issues                           |
| KICS       | Scans Terraform, Kubernetes, Docker, and more                           |
| TFLint     | Linter for Terraform code quality and best practices                    |
| OPA        | Policy engine for enforcing rules in CI/CD and IaC workflows            |
| Bridgecrew | Platform built around Checkov for IaC governance                        |

---

## 📘 Example Secure Terraform Snippet

```hcl
resource "aws_security_group" "web_sg" {
  name        = "web_sg"
  description = "Allow HTTPS access"

  ingress {
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    cidr_blocks = ["203.0.113.0/24"] # Restrictive range
  }

  egress {
    from_port   = 0
    to_port     = 0
    protocol    = "-1"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

---

## 🎯 Summary

IaC security is essential in preventing configuration drift, misconfigurations, and embedded vulnerabilities. By embedding security into the code lifecycle ("Shift Left"), you can reduce the risk before infrastructure is deployed.

---

## 📚 References

* [Checkov GitHub](https://github.com/bridgecrewio/checkov)
* [tfsec](https://aquasecurity.github.io/tfsec/)
* [KICS by Checkmarx](https://kics.io/)
* [Open Policy Agent (OPA)](https://www.openpolicyagent.org/)
