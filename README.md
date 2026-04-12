<div align="center">
  
#  Python Password Entropy
**A Cryptographic CLI Utility for Verifiable Credential Security & Breach Detection**

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Security](https://img.shields.io/badge/Security-NIST_SP_800--63B-success.svg)]()
[![Core Libs](https://img.shields.io/badge/Dependencies-Zero-purple.svg)]()
[![CLI Tool](https://img.shields.io/badge/Interface-CLI-darkgray.svg)]()



</div>

##  Overview
**Python Password Entropy** is a standalone, command-line utility designed to enforce modern cryptographic policy standards across development and operations environments. 

Moving beyond obsolete, arbitrary rules-based validation (e.g., "must contain one special character"), this tool calculates **mathematically verifiable security metrics**. It is built specifically for SecOps teams, backend developers, and security auditors who require absolute assurance regarding the strength and integrity of their application keys and user credentials.

##  Key Engineering Features

*  **Mathematical Entropy Calculation:** Calculates true cryptographic entropy (Shannon entropy) based on character pool size and length, neutralizing predictable generation patterns.
*  **NIST SP 800-63B Compliance:** Aligns with modern National Institute of Standards and Technology (NIST) digital identity guidelines, favoring credential length and complexity over frustrating character-composition rules.
*  **Secure Compromise Detection:** Features a `--breach` flag to actively audit credentials against known data breaches without exposing the plaintext password (utilizing secure cryptographic hashing).
*  **Zero Supply-Chain Risk:** Built entirely on Python's core security libraries (`secrets`, `hashlib`). By eliminating external dependencies, it removes the risk of third-party package vulnerabilities.

---

##  Technology Stack

| Component | Technology | Purpose |
| :--- | :--- | :--- |
| **Core Logic** | Python 3 | High-performance script execution |
| **Cryptography** | `hashlib` | Secure, one-way hashing for breach verification |
| **Randomization** | `secrets` | Cryptographically strong random number generation (CSPRNG) |
| **Interface** | CLI | Headless execution for CI/CD pipelines and server environments |

---

##  Getting Started

Because this utility relies strictly on Python's standard library, there are **zero external packages to install**.

```bash
# 1. Clone the repository
git clone 
cd Python-Password-Entropy

# 2. Run the tool 
python app.py -h : Cli commands help.
python app.py passphrase : Generate a secure, memorable mnemonic passphrase (Diceware style).
python app.py key : Generate a secure cryptographic key (hex-encoded).
python app.py token : Generate a URL-safe, base64-encoded token.
python app.py password : Generate a secure, high-entropy password.
python app.py audit --breach "Your_Password" : Check if the password has been found in known data breaches (K-Anonymity check).
python app.py audit "Your_Password" : Assess the cryptographic strength (Entropy and Breach Status) of a given secret.
