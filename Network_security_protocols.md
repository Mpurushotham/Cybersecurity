# 🌐 Network Security & Protocols

## Overview

Network security focuses on protecting the integrity, confidentiality, and availability of data during transmission. This involves using protocols, tools, and architectures that ensure secure communication across local and wide area networks.

---

## 🔐 Key Protocols & Their Security Roles

| Protocol | Port(s)  | Purpose                    | Security Features                                  |
| -------- | -------- | -------------------------- | -------------------------------------------------- |
| HTTPS    | 443      | Secure web traffic         | TLS encryption, certificate-based authentication   |
| SSH      | 22       | Secure remote access       | Encrypted terminal sessions, key-based login       |
| SFTP     | 22       | Secure file transfer       | SSH-based, encrypted data and authentication       |
| FTPS     | 990      | FTP over SSL               | SSL/TLS encryption for FTP                         |
| IPSec    | 500/4500 | Secure IP communication    | Tunnel mode, encryption, authentication            |
| TLS/SSL  | Varies   | Encryption layer for apps  | Integrity, confidentiality, certificate validation |
| DNSSEC   | 53       | Secure DNS                 | Origin authentication, data integrity              |
| VPN      | Varies   | Secure remote connectivity | Encryption, tunneling, IP masking                  |

---

## 🛡️ Common Network Attacks & Defenses

| Attack Type                          | Description                                           | Defense Mechanism                                  |
| ------------------------------------ | ----------------------------------------------------- | -------------------------------------------------- |
| MITM (Man-in-the-Middle)             | Attacker intercepts and possibly alters communication | Use encryption (TLS), certificate pinning          |
| DDoS (Distributed Denial of Service) | Overloads systems/networks with traffic               | Rate-limiting, firewalls, DDoS protection services |
| ARP Spoofing                         | Fake ARP messages to redirect traffic                 | Use static ARP, switch port security               |
| DNS Poisoning                        | Redirects DNS queries to malicious sites              | DNSSEC, cache poisoning prevention                 |
| Packet Sniffing                      | Capturing unencrypted network traffic                 | Use encrypted protocols (SSH, HTTPS, TLS)          |

---

## 🧰 Tools for Network Security Analysis

* **Wireshark** – Deep packet inspection
* **tcpdump** – CLI-based packet capture
* **Nmap** – Network mapping and port scanning
* **Snort/Suricata** – Network intrusion detection
* **Zeek (formerly Bro)** – Network security monitoring

---

## 🌍 Secure Network Architecture Principles

* **Segmentation** – Use VLANs and firewalls to separate traffic
* **Least Privilege Access** – Limit network access to only required systems
* **Zero Trust Model** – Never trust, always verify, even inside the network
* **Encryption Everywhere** – Secure data at rest and in transit
* **Regular Audits & Monitoring** – Identify anomalies and unauthorized access

---

## 📖 Learning Resources

* [Cisco CyberOps Associate](https://www.cisco.com/c/en/us/training-events/training-certifications/certifications/associate/cyberops.html)
* [CompTIA Network+](https://www.comptia.org/certifications/network)
* [Wireshark Tutorials](https://www.wireshark.org/docs/)
* [NIST SP 800-115](https://csrc.nist.gov/publications/detail/sp/800-115/final) – Technical Guide to Information Security Testing

---

## 🧠 Summary

Network security and protocols form the foundation of secure communications. Understanding ports, encryption, common threats, and architectural best practices is essential for any cybersecurity or cloud professional.
