# SOC Cryptographic Playbook
Defensive Security Operations and Incident Response Automation

* **Author:** Obioma Felicity Uzoh
* **Role:** Security Operations Center (SOC) Analyst
* **Focus Area:** Defensive Security Operations, Incident Triage, and Blue Team Automation

---

## The Problem
During incident triage, analysts regularly encounter hidden payloads, raw log files, and live malicious indicators. Processing these under pressure using unverified, ad-hoc web tools introduces severe operational risks—including accidental malware execution, alert pollution, and insecure data handling.

This repository provides a standardized, peer-reviewed collection of CyberChef recipes paired with an interactive frontend dashboard to instantly load optimized, production-grade workflows for everyday incident response and data protection.

---

## Interactive Playbook Directory
Click on any operational module below to access its local documentation and pre-configured JSON recipe file. You can run these instantly via the [Interactive Web](https://techounik.github.io/CyberChef-Recipes-Playbook/) Dashboard hosted on GitHub Pages.

### 📂 [Decoding](Decoding/)
* **What it does:** Unpacks strings or scripts that attackers obfuscate to bypass network security filters.

* **When to triage:** Use when encountering nested Base64 strings, URL-encoded patterns, or suspicious script blocks in email headers and traffic logs.

### 📂 [Hashing](Hashing/)
* **What it does:** Generates MD5, SHA-1, and SHA-256 signatures simultaneously to verify file integrity.

* **When to triage:** Use to generate cryptographic fingerprints for unknown binaries or artifacts to check against threat intelligence blacklists (IoCs).

### 📂 [Encryption](Encryption/)
* **What it does:** Enforces data-at-rest confidentiality using a password-derived PBKDF2 key pipeline and standard AES-256-CBC encryption.

* **When to triage:** Use to securely lock sensitive forensic notes, malware analysis data, or internal databases before storage or transit.

### 📂 [Threat Intel Folder](Threat%20Intel%20Defanging/)
* **What it does:** Sanitizes live URLs, domains, and IP addresses (e.g., converting http:// to hxxp:// and 1.1.1.1 to 1[.]1[.]1[.]1).

* **When to triage:** Use before pasting raw threat infrastructure indicators into shared communication channels, tickets, or reports to eliminate accidental click risks.

### 📂 [Log Parsing](Log20%Parsing/)
* **What it does:** Drops system noise using specific filtering patterns to isolate a clean, deduplicated list of network targets.

* **When to triage:** Use when analyzing massive firewall logs or authentication events to extract unique IPv4/IPv6 addresses instantly.

---

## Defensive Architecture Blueprint
For data-at-rest protection, all encryption recipes in this toolkit enforce a strict mathematical sequence:

```Plaintext

[User Password Input] -> [Add Random Salt] -> [Run PBKDF2/SHA256 Key Tool] -> [Run AES-256-CBC Encryption Engine] -> [Secure Encrypted Ciphertext Output]
```

This design ensures that even if an attacker steals the final encrypted data, they cannot break it through brute-force guessing because the mathematical structure and the key setup are too strong.

---

## Disclaimer
This repository contains standardized workflows intended strictly for authorized defensive security operations, incident response triage, and educational research. The author assumes no liability for unauthorized modifications or misuse of these templates.
