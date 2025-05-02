# 🔐 Secure Coding & OWASP Top 10

## ✍️ What is Secure Coding?

Secure coding is the practice of writing software with attention to protecting data, maintaining confidentiality, and preventing security flaws such as injection, XSS, or insecure storage.

---

## 🔟 OWASP Top 10 (2021 Edition)

1. **Broken Access Control** – Bypassing restrictions via insecure direct object references (IDOR).
2. **Cryptographic Failures** – Poor or no encryption of sensitive data.
3. **Injection** – SQL, NoSQL, OS command injection.
4. **Insecure Design** – Missing security controls, flawed business logic.
5. **Security Misconfiguration** – Default credentials, open S3 buckets.
6. **Vulnerable & Outdated Components** – Libraries with known exploits.
7. **Identification & Authentication Failures** – Broken login, brute-force.
8. **Software and Data Integrity Failures** – CI/CD misuse, unsigned code.
9. **Security Logging & Monitoring Failures** – No alerts, insufficient logs.
10. **Server-Side Request Forgery (SSRF)** – Internal system access via crafted requests.

---

## 🧰 Secure Coding Practices

* Validate all inputs (whitelisting preferred)
* Use parameterized queries
* Apply least privilege principle
* Store passwords using strong hashing (e.g., bcrypt)
* Avoid hardcoding credentials or secrets
* Use secure headers (Content-Security-Policy, X-Content-Type-Options)
* Apply secure defaults and sanitize outputs

---

## 📌 Example

```python
# ❌ Insecure
query = "SELECT * FROM users WHERE name = '" + user_input + "'"

# ✅ Secure
cursor.execute("SELECT * FROM users WHERE name = %s", (user_input,))
```

---

## 🧪 Tools

* Static Code Analysis: SonarQube, Semgrep
* Dependency Scanning: OWASP Dependency-Check, Snyk
* DAST/SAST: ZAP, Burp Suite, GitHub Advanced Security

---

## 📚 References

* [OWASP Top 10 2021](https://owasp.org/Top10/)
* [Cheat Sheet Series](https://cheatsheetseries.owasp.org/)
* [Secure Coding Guidelines (Microsoft)](https://learn.microsoft.com/en-us/security/develop/secure-coding-guidelines)
