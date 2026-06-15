# SOC Cryptographic Playbook
Defensive Security Operations and Incident Response Automation

**Author:** Obioma Felicity Uzoh
**Role:** Security Operations Center (SOC) Analyst
**Focus Area:** Defensive Security Operations, Incident Triage, and Blue Team Automation

---

## Operational Problem Solved
During security incident triage and threat hunting, SOC analysts frequently find hidden payloads, unusual encoding types, raw log text, and sensitive data that must be safely stored. Relying on unverified decoding or encryption methods creates serious security risks:

1. **Accidental Execution:** Copying and pasting raw malicious links or IP addresses can cause analysts to accidentally connect to dangerous sites or pollute internal security alerts.

2. **Implementation Flaws:** Setting up encryption rules manually while under pressure often leads to weak keys, missing salts, or insecure cipher choices.

3. **Operational Inefficiency:** Analysts waste important minutes during severe security incidents trying to build text extraction tools from scratch.

This project solves these problems by providing a standardized collection of pre-configured CyberChef recipes paired with an interactive web dashboard. It allows tier-1 and tier-2 defensive analysts to instantly load optimized workflows for daily incident response and data protection tasks.

---

## Repository Structure
The playbook is organized into separate folders based on specific security tasks:

Plaintext
├── index.html                   # Interactive Playbook Dashboard
├── README.md                    # Core Playbook Documentation
├── Decoding/                    # Folder for hidden text and script decoding recipes
├── Hashing/                     # Folder for file integrity and signature checking recipes
├── Encryption/                  # Folder for data protection and secure key recipes
├── Threat Intel Defanging/      # Folder for sanitizing dangerous links and IP addresses
└── Log Parsing/                 # Folder for filtering background noise from raw network logs

---

## Core Operational Modules and Recipes
1. **Decoding (/Decoding)**
- *Purpose:* Cleans up hidden or obfuscated text found in network traffic logs, malicious document scripts, or software analysis tasks.
- *Recipe Focus:* Handles complex steps like combining Base64 decoding with URL decoding.

2. **Hashing (/Hashing)**
- *Purpose:* Verifies that files have not been changed and creates cryptographic signatures to match against known lists of threats.
- *Recipe Focus:* Generates MD5, SHA-1, and SHA-256 hash values at the same time for any text or file.

3. **Encryption (/Encryption)**
- *Purpose:* Sets up strong data confidentiality rules to protect sensitive forensic evidence or local databases stored on a disk.
- *Recipe Focus:* Uses standard AES-256 encryption in CBC mode, powered by a password-based PBKDF2 key derivation system with an added salt to stop password-cracking tools.

4. **Threat Intel Defanging (/Threat Intel Defanging)**
- *Purpose:* Sanitizes live malicious links and indicators before they are added to documentation, reports, or communications.
- *Recipe Focus:* Automatically breaks active links by changing text like http to hxxp and placing brackets around IP addresses, such as converting 192.168.1.1 to 192[.]168[.]1[.]1.

5. **Log Parsing (/Log Parsing)**
- *Purpose:* Speeds up analysis by searching through messy text logs to isolate key security information.
- *Recipe Focus:* Uses text filtering patterns to strip away system background noise and create a clean list of unique IPv4 and IPv6 addresses from raw logs.

---

## How to Deploy and Use This Playbook
1.  **Method A: Interactive Web Dashboard (Recommended)**
- *Host via GitHub Pages:* Go to your GitHub repository settings, turn on GitHub Pages, and select your main code branch.
- *Live Access:* Open the mobile-responsive user interface using the index.html file from any device.
- *Execution:* Click the "Launch Recipe" button on any card. The link will open CyberChef in your browser with the exact tool configurations already loaded.

2. **Method B: Manual Recipe Import**
- Open the specific folder for the tool you need inside this repository.
- Open the JSON recipe file and copy all the text inside it.
- Open your local or web-based CyberChef application.
- Click Open Recipe or paste the copied JSON text directly into the Recipe column to load the tool setup instantly.

---

## Defensive Architecture Blueprint
For protecting data stored on a system, all automation recipes in this repository follow this strict step-by-step cryptographic pipeline:

Plaintext

```[User Password Input] -> [Add Random Salt] -> [Run PBKDF2/SHA256 Key Tool] -> [Run AES-256-CBC Encryption Engine] -> [Secure Encrypted Ciphertext Output]```

This design ensures that even if an attacker steals the final encrypted data, they cannot break it through brute-force guessing because the mathematical structure and the key setup are too strong.
