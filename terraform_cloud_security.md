# 🌍 Terraform for Cloud Security

## 🔐 What is Terraform?

Terraform is an open-source Infrastructure as Code (IaC) tool by HashiCorp that allows you to provision and manage infrastructure across multiple cloud providers using a declarative configuration language (HCL).

---

## 🛡️ Why Use Terraform for Security?

* **Standardization**: Enforce consistent security policies across environments.
* **Automation**: Automate security resource provisioning (e.g., firewalls, IAM roles).
* **Version Control**: Track changes and audit configurations.
* **Scalability**: Secure multi-cloud environments from a central source.

---

## 📁 Key Use Cases

### 1. **IAM Policies & Roles**

* Define users, roles, and policies in Azure, AWS, GCP.
* Ensure least privilege principles.

```hcl
resource "aws_iam_policy" "readonly" {
  name   = "ReadOnlyPolicy"
  policy = file("readonly_policy.json")
}
```

### 2. **Security Groups / Network Rules**

* Configure inbound/outbound rules for applications.
* Block public access by default.

```hcl
resource "aws_security_group" "web" {
  name        = "web_sg"
  description = "Allow web traffic"

  ingress {
    from_port   = 443
    to_port     = 443
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
}
```

### 3. **Encryption & Key Management**

* Create and manage KMS keys in cloud.
* Enforce encryption for S3, Azure Blob, GCS buckets.

```hcl
resource "aws_kms_key" "example" {
  description         = "My KMS key"
  deletion_window_in_days = 10
  enable_key_rotation     = true
}
```

### 4. **Logging & Monitoring**

* Enable CloudTrail, Monitor, Logging on resources.
* Route logs to SIEM tools (e.g., Sentinel, Splunk).

```hcl
resource "aws_cloudtrail" "example" {
  name                          = "example-trail"
  s3_bucket_name                = aws_s3_bucket.log_bucket.id
  include_global_service_events = true
  is_multi_region_trail         = true
}
```

### 5. **Compliance & Policy as Code**

* Integrate with tools like:

  * **Terraform Sentinel** for policy enforcement.
  * **OPA/Conftest/Checkov** for IaC security scanning.

---

## 🔄 Integration into CI/CD Pipelines

* Use `terraform plan` and `terraform apply` with automated security checks.
* Include `tfsec`, `Checkov`, `OPA` as part of pull request workflows.

```yaml
# Example GitHub Action step
- name: Run Checkov scan
  uses: bridgecrewio/checkov-action@master
  with:
    directory: ./terraform
```

---

## 🧪 Best Practices

* Use modules for reusable security components.
* Store secrets in Key Vaults, not in code.
* Review Terraform state files for sensitive data.
* Enable remote state with locking (e.g., S3 + DynamoDB).
* Use `terraform fmt`, `validate`, `plan`, and security tools in pipelines.

---

## 📚 References

* [Terraform Docs](https://www.terraform.io/docs)
* [Checkov by Bridgecrew](https://www.checkov.io/)
* [OPA - Open Policy Agent](https://www.openpolicyagent.org/)
* [tfsec](https://aquasecurity.github.io/tfsec/)
