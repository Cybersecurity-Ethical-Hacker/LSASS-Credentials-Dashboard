# LSASS Credentials Dashboard 🔑

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![GitHub Issues](https://img.shields.io/github/issues/Cybersecurity-Ethical-Hacker/LSASS-Credentials-Dashboard)](https://github.com/Cybersecurity-Ethical-Hacker/LSASS-Credentials-Dashboard/issues)
[![GitHub Stars](https://img.shields.io/github/stars/Cybersecurity-Ethical-Hacker/LSASS-Credentials-Dashboard)](https://github.com/Cybersecurity-Ethical-Hacker/LSASS-Credentials-Dashboard/stargazers))
[![Contributions Welcome](https://img.shields.io/badge/Contributions-Welcome-brightgreen.svg)](CONTRIBUTING.md)

🔐 LSASS memory dumps contain a goldmine of credential data but extracting actionable insights quickly is a challenge. The LSASS Credentials Dashboard transforms raw dump files into clear, prioritized intelligence for security teams.

## 📸 Screenshot:
![lsass](https://github.com/user-attachments/assets/4a17a72d-1d5f-40eb-aed7-22de5182141d)
![lsass2](https://github.com/user-attachments/assets/f27bec90-2a38-455b-aff9-c6023b75e002)

## 🔍 Data Collected & Analyzed:
USER, DOMAIN, HOST, LOGON TIME, SID, AUTH ID, SESSION ID, NT HASH, KERBEROS, DPAPI, OTHER CREDS...

## 🚨 Risk Prioritization:
RISK: Flags for:
- ✅ Domain Admins (SID-500)
- 🔓 Cleartext passwords (Kerberos)
- 🚩 NULL hashes (31d6cfe0d16ae931b73c59d7e0c089c0)
- ♻️ Reused hashes (highlighted when NT hash appears >1x)

PWN: Quick-visual icons for:
- 🔑 Credential exposure
- ⚠️ DPAPI key overload
- ☁️ CloudAP/single-sign-on (SSO) artifacts

## 🌟 For penetration testers:

- 🔓 Prioritizing High-Value Targets
Auto-flags Domain Admins (SID-500) and cleartext Kerberos passwords
Highlights service accounts (ending with $) and NULL hashes for easy privilege escalation paths

- 🔄 Password Reuse Detection
Identifies reused NT hashes across accounts—critical for lateral movement
Exposes weak credential hygiene (e.g., shared local admin passwords)

- 🔑 DPAPI & Kerberos Analysis
Extracts DPAPI master keys and GUIDs for decrypting saved credentials (e.g., browser logins, saved RDP sessions)
Reveals Kerberos encryption types (e.g., RC4 with no pre-auth) and ticket expiry times

- 📊 Operational Efficiency
Filters noise (e.g., system accounts like SYSTEM, NETWORK SERVICE) to focus on exploitable credentials
Exportable data (via copy/paste) for integration with tools like Mimikatz, CrackMapExec, or hashcat

Ideal for:<br>
✔️ Rapidly assessing credential exposure during engagements<br>
✔️ Planning attack chains based on reused hashes or weak configurations<br>
✔️ Reporting clear evidence of credential risks to clients

This tool helps you:
- 🔍 Quickly identify high-value targets during investigations
- 📊 Understand credential exposure across your environment
- ⏱ Save hours of manual analysis during incident response

## 🚀 Usage
Simply feed the tool PyPykatz JSON output, and let the dashboard do the rest!
Export your LSASS dump to JSON using PyPykatz:

📍 Command-Line Options:
```bash
pypykatz lsa minidump lsass.dump -o creds.json --json
```
Upload the `creds.json` file to the dashboard.

## 💡 Key Security Benefit:
The tool runs entirely in your browser and your sensitive credential data never leaves your machine.

## 📂 Directory Structure
- `lsass.html`: Main file to load in browser.

## 🤝 Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements, bug fixes, or new features.

## 🛡️ Ethical Usage Guidelines
I am committed to promoting ethical practices in cybersecurity. Please ensure that you use this tool responsibly and in accordance with the following guidelines:

1. Educational Purposes Only
This tool is intended to be used for educational purposes, helping individuals learn about penetration testing techniques and cybersecurity best practices.

2. Authorized Testing
Always obtain explicit permission from the system owner before conducting any penetration tests. Unauthorized testing is illegal and unethical.

3. Responsible Vulnerability Reporting
If you discover any vulnerabilities using this tool, report them responsibly to the respective organizations or maintainers. Do not exploit or disclose vulnerabilities publicly without proper authorization.

4. Compliance with Laws and Regulations
Ensure that your use of this tool complies with all applicable local, national, and international laws and regulations.

## 📚 Learn and Grow
Whether you’re a penetration tester hunting for lateral movement paths, a blue teamer investigating credential exposure, or a forensic analyst dissecting LSASS dumps, the LSASS Credentials Dashboard transforms raw memory dumps into actionable intelligence helping you uncover hidden risks, prioritize remediation, and secure your environment with precision.

> [!NOTE]
> Let’s build a safer web together! 🌐🔐
