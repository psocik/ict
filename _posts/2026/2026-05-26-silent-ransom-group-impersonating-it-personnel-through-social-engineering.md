---
title: Silent Ransom Group Impersonating IT Personnel through Social Engineering
date: 2026-05-26
categories: [CYBERSECURITY]
tags: [SILENT RANSOM GROUP,SOCIAL ENGINEERING,CYBERSECURITY,DATA EXFILTRATION]
---

## Silent Ransom Group Targeting Law Firms 🚨

The **Silent Ransom Group (SRG)**, also known as Luna Moth, Chatty Spider, and UNC3753, is actively targeting law firms through sophisticated social engineering techniques. They utilize phone calls and phishing emails, impersonating IT support to gain access to victim computers and exfiltrate sensitive data. This is typically done using legitimate remote access tools or by sending an individual in-person to the victim's location to gain physical access to computers.

### Key Tactics of SRG 🔍

- **Phishing Emails & Phone Calls:** SRG actors pose as IT department employees, urging victims to grant access to remote desktop sessions.
- **In-Person Threats:** If remote access fails, they may send a threat actor to physically access the victim's computer.
- **Data Exfiltration:** Once access is obtained, they quickly escalate privileges and exfiltrate data without encryption, often using tools like WinSCP or Rclone.

### Industries Affected 🏢

While SRG has targeted various sectors, they have consistently focused on US-based law firms since Spring 2023. Their operations have been ongoing since at least 2022, and they conduct data theft and extortion without relying on traditional ransomware methods.

### Recommendations to Protect Your Organization 🛡️

The FBI recommends several actions to defend against SRG threat actors:
- Verify the credentials of all individuals accessing company spaces.
- Develop policies regarding IT support communication and authentication.
- Conduct staff training on identifying and reporting phishing attempts.
- Maintain regular backups of company data.
- Implement phishing-resistant multi-factor authentication (MFA).
- If possible, block access to port 22 and disable remote access on sensitive computers.

For more detailed information, you can read the full article [here](https://www.ic3.gov/CSA/2026/260526.pdf).