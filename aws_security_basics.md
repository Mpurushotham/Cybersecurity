# ☁️ AWS Security Fundamentals

Focused overview of security services and features available in AWS to protect identities, monitor environments, and secure data.

---

## 🔐 1. IAM (Identity and Access Management)

### What It Is:
Central service to manage access to AWS services and resources securely.

### Key Features:
- Users, Groups, Roles
- IAM Policies (JSON-based permission statements)
- Fine-grained access control
- MFA, Role Assumption, Federation

### Use Case:
Create a role with limited S3 permissions that an EC2 instance can assume for secure file uploads.

---

## 🛡️ 2. GuardDuty

### What It Is:
Threat detection service that continuously monitors for malicious or unauthorized behavior.

### Key Features:
- Detects crypto mining, unusual logins, reconnaissance
- Analyzes CloudTrail, VPC Flow Logs, and DNS logs
- Integrates with AWS Security Hub, Lambda for automated response

### Use Case:
Alert triggered when an instance communicates with a known botnet IP.

---

## 🔐 3. AWS Key Management Service (KMS)

### What It Is:
Fully managed service to create and manage cryptographic keys for data encryption.

### Key Features:
- CMKs (Customer Master Keys) with automatic rotation
- Envelope encryption (data keys + CMKs)
- Integrated with S3, EBS, RDS, Lambda, etc.

### Use Case:
Encrypt all objects uploaded to an S3 bucket using a KMS-managed key.

---

## 📜 4. AWS CloudTrail

### What It Is:
A logging service that records API activity across AWS services for governance, compliance, and auditing.

### Key Features:
- Captures events across all AWS accounts
- Sends logs to S3 for long-term storage
- Integrates with CloudWatch Logs for real-time analysis

### Use Case:
Audit who deleted an EC2 instance or who modified an S3 bucket policy.

---

## 🧠 Additional AWS Security Services:

| Service            | Functionality                                      |
|--------------------|---------------------------------------------------|
| AWS Config         | Tracks resource configuration history             |
| AWS Inspector      | Automatically assesses EC2 and Lambda for vulns   |
| AWS Security Hub   | Aggregates security findings from multiple tools  |
| Amazon Macie       | Classifies and protects sensitive data (e.g. PII) |
| AWS WAF & Shield   | Protects apps from DDoS and web exploits          |

---

## 🧪 Lab Practice Ideas:
- Create IAM policies using least privilege principle
- Simulate GuardDuty alerts using sample data
- Enable KMS encryption for S3 buckets
- Track changes in AWS environment using CloudTrail and Config

---

## 📚 References:
- [IAM Documentation](https://docs.aws.amazon.com/iam/)
- [GuardDuty Docs](https://docs.aws.amazon.com/guardduty/)
- [AWS KMS Docs](https://docs.aws.amazon.com/kms/)
- [CloudTrail Docs](https://docs.aws.amazon.com/cloudtrail/)
