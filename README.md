# CyberTech Inc. SOC Simulation - Final Project

---

## 📌 About The Project

This project is a **Security Operations Center (SOC)** simulation for CyberTech Inc., a 500-employee financial company. The scope includes:

- Lab environment setup (VirtualBox, Kali Linux, Windows 10, Metasploitable 2)
- Risk assessment (NIST RMF)
- Security policy creation (Access, Password, Incident Response)
- Wazuh SIEM installation and configuration
- Penetration testing (Reconnaissance, Exploit, Post-Exploit)
- Incident response (NIST SP 800-61)
- Reporting

---

## 🏗️ Lab Architecture

| VM | Role | IP |
|----|------|----|
| Kali Linux | Attacker / Pentest | 192.168.1.75 |
| Windows 10 | Target System | 192.168.1.95 |
| Metasploitable 2 | Vulnerable Target | 192.168.1.93 |
| Wazuh SIEM | Log Collection & Analysis | 192.168.1.50 |
| Suricata NIDS | Network Intrusion Detection | 192.168.1.46 |

---

## 🔐 Security Policies

| Policy | Document ID |
|--------|-------------|
| Access Control Policy | CT-POL-001 |
| Password Policy | CT-POL-002 |
| Incident Response Policy | CT-POL-003 |

---

## 🛡️ Attack Scenarios

### Windows 10 (192.168.1.95)
1. **Reconnaissance:** Nmap port scan (445)
2. **Initial Access:** NetExec SMB Brute-Force → Administrator:1234567
3. **Defense Evasion:** UAC Bypass, Defender Disabling
4. **Credential Access:** SAM/LSA Dump (6 NTLM hashes + DPAPI)
5. **Lateral Movement:** Pass-the-Hash, PsExec, Evil-WinRM

### Metasploitable 2 (192.168.1.93)
1. **Reconnaissance:** Nmap -sV (vsftpd 2.3.4 detection)
2. **Exploit:** vsftpd 2.3.4 backdoor (CVE-2011-2523) → Root Shell
3. **Post-Exploit:** /etc/shadow exfiltration
4. **Credential Cracking:** John the Ripper offline hash cracking (3 accounts)
5. **Web Exploit:** DVWA SQL Injection (Union/Error-based)

---

## 📊 SIEM Detections

| Attack | Rule ID | Level |
|--------|---------|-------|
| Brute-Force | 100026 | 12 |
| Pass-the-Hash | 100080 | 14 |
| PsExec Hidden PowerShell | 100082 | 14 |
| vsftpd Backdoor | 100047 | 12 |
| SQL Injection | 100050 / 100051 | 12 |

---

## 📂 File List

| File | Description |
|------|-------------|
| `0_Pentest_SIEM_Analiz_Raporu.pdf` | Pentest and SIEM Analysis Report |
| `IR_Olay_Mudahale_Raporu.pdf` | Incident Response Report (NIST SP 800-61) |
| `CT-RA-001_Risk_Degerlendirme.pdf` | Risk Assessment Report (NIST RMF) |
| `CT-POL-001_Erisim_Kontrol_Politikasi.pdf` | Access Control Policy |
| `CT-POL-002_Sifre_Politikasi.pdf` | Password Policy |
| `CT-POL-003_Olay_Mudahalesi_Politikasi.pdf` | Incident Response Policy |
| `Asset_Inventory-CyberTech_Inc.pdf` | Asset Inventory |
| `CyberTech_A.S._Profili.pdf` | Company Profile |
| `Metasploitable_OpenVAS_Report.pdf` | OpenVAS Vulnerability Scan Report |

---

## 🎯 Frameworks Used

- **NIST SP 800-61 Rev.3** — Incident Response
- **MITRE ATT&CK v15** — Attack Tactics/Techniques
- **NIST CSF 2.0** — Security Functions (Protect/Detect/Respond/Recover)
- **NIST RMF** — Risk Assessment

---

## 👩‍💻 Author

**Arzum Enfal Kulaksız**  

---

## 📅 Date

**April 2026**

---

**TLP: CLEAR** — Freely shareable.
