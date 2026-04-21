# GRC Risk Assessment Lab Report

# Executive Summary

This lab focused on moving from technical scanning to proper risk understanding in a GRC context.

The goal was to identify vulnerabilities using tools like Nmap, Nikto, and Nuclei, and then explain what those findings mean from a risk and business point of view.

During the lab, several issues were identified on the Metasploitable 2 system. Open services like FTP, Telnet, and HTTP were discovered, along with outdated software and known vulnerabilities such as the vsftpd backdoor (CVE-2011-2523).

These findings show that the system has a wide attack surface and weak security configuration.

The results were then mapped to frameworks like NIST Cybersecurity Framework and CIS Controls. Risk was assessed based on impact and likelihood, and financial exposure was calculated using SLE and ALE. A business impact analysis was also carried out to understand how these risks affect operations.

---

# Key Findings

- vsftpd 2.3.4 backdoor (CVE-2011-2523)  
- Telnet transmitting credentials in plaintext  
- Default credentials in DVWA  
- Outdated Apache, PHP, and MySQL  

---

# Recommendations

- Disable insecure services (FTP, Telnet)  
- Patch vulnerable systems  
- Enforce strong authentication  
- Apply CIS hardening standards  

---

# Methodology

The lab followed a structured approach.

The system was first scanned using Nmap to identify open ports and services. This helped define the attack surface.

Next, Nikto and Nuclei were used to identify web vulnerabilities and known CVEs.

After that, findings were analyzed using GRC frameworks to understand risk and compliance gaps.

Then, quantitative analysis was carried out using SLE and ALE to estimate financial impact.

Finally, a business impact analysis was done to understand how these risks affect operations.

---

# Task 1: Nmap Scan

## Results

- Open ports: 21, 22, 23, 25, 80, 3306  
- vsftpd 2.3.4 with anonymous access  
- Apache 2.2.8 (outdated)  
- Telnet exposed  

## Analysis

The system exposes multiple services, increasing the attack surface.

Outdated software and insecure protocols create clear entry points for attackers.

---

# Task 2: Web Scanning

## Findings

- Exposed directories: /dvwa, /phpmyadmin  
- HTTP TRACE enabled  
- Default credentials present  
- CVE-2011-2523 detected  
- Apache DoS vulnerability  

## Analysis

The system is poorly configured and exposes sensitive components.

Default credentials and known vulnerabilities increase the risk of compromise.

---

# Risk Assessment

| Finding | Risk Level | Business Impact |
|--------|-----------|----------------|
| vsftpd Backdoor | High | Full system compromise |
| Telnet Exposure | High | Credential theft |
| Weak Credentials | High | Unauthorized access |
| HTTP TRACE | Medium | Information disclosure |

---

# Quantitative Risk (SLE & ALE)

| Risk | SLE | ALE |
|-----|-----|-----|
| FTP Backdoor | $450,000 | $225,000 |
| Credential Exposure | $210,000 | $210,000 |
| Weak Credentials | $240,000 | $168,000 |

## Analysis

These risks have direct financial impact and must be addressed.

---

# Risk Treatment

- Patch vulnerable services  
- Disable insecure protocols  
- Enforce authentication controls  
- Update systems regularly  

---

# Control Mapping (NIST 800-53)

- SI-2 → Flaw remediation  
- AC-6 → Least privilege  
- SC-13 → Cryptographic protection  
- AC-2 → Account management  

---

# Business Impact Analysis

| Risk | Process | Impact |
|-----|--------|--------|
| FTP Backdoor | Server Operations | Loss of control |
| Credential Exposure | Authentication | Data breach |
| Weak Credentials | Web Access | Unauthorized access |

---

# Final Executive Summary

The system contains multiple high-risk vulnerabilities.

These issues expose the organization to system compromise, data breaches, and financial loss.

Estimated losses range between $168,000 and $225,000 annually.

## Actions Required

- Patch systems immediately  
- Disable insecure services  
- Enforce strong authentication  

---

# Conclusion

This lab shows the full process from technical scanning to risk analysis.

The system is not secure in its current state.

Fixing these issues will reduce both technical risk and business impact.

---

# Declaration

I confirm that this report is my own work.

**Signature:**  
**Date:** 13th April, 2026  
