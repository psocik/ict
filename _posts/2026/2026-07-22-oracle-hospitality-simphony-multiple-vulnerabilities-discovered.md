---
title: Oracle Hospitality Simphony Multiple Vulnerabilities Discovered
date: 2026-07-22
categories: [SECURITY]
tags: [ORACLE,VULNERABILITIES,HOSPITALITY,SECURITY]
---

## Oracle Hospitality Simphony Multiple Vulnerabilities Discovered 🚨

Oracle's July 2026 Critical Patch Update addresses four remotely exploitable vulnerabilities affecting Oracle Hospitality Simphony. Discovered and responsibly disclosed by Horizon3.ai researcher Jimi Sebree, these vulnerabilities impact two Simphony components: the EGateway Printing Handler and the Kiosk application. Together, they provide multiple paths for unauthenticated attackers to compromise vulnerable systems, including NTLM hash disclosure, arbitrary file writes, authentication bypass, and arbitrary code execution.

### Vulnerabilities Overview:
- **CVE-2026-60167**: UNC path coercion resulting in NTLM hash disclosure.
- **CVE-2026-60168 & CVE-2026-60169**: Related vulnerabilities enabling arbitrary file writes through the EGateway Printing Handler.
- **CVE-2026-60170**: Authentication bypass affecting the Simphony Kiosk application, potentially leading to arbitrary code execution.

Oracle Hospitality Simphony is widely deployed across hospitality chains, quick-service restaurants, stadiums, casinos, hotels, and other food service environments. Successful exploitation may enable lateral movement, persistence, credential compromise, or complete host compromise. Currently, there are no confirmed reports of active exploitation in the wild.

### Detailed Vulnerability Analysis:
- **CVE-2026-60167** affects the EGateway Printing Handler. Improper validation of user-controlled input allows an unauthenticated attacker to supply a crafted UNC path that causes the Simphony host to initiate an outbound SMB connection to an attacker-controlled server. Windows may automatically transmit NTLM authentication material during this connection, which could lead to credential compromise.
- **CVE-2026-60168 and CVE-2026-60169** result from insufficient validation of attacker-controlled input before file operations are performed, allowing arbitrary files to be written to the underlying host.
- **CVE-2026-60170** allows an unauthenticated attacker to bypass authentication and gain access to the Kiosk administrator console, enabling arbitrary code execution.

Oracle identifies the following supported Oracle Hospitality Simphony versions as affected by these vulnerabilities: 19.8 through 19.8.5, 19.9 through 19.9.3, and 19.10. Oracle addressed all four vulnerabilities in the July 2026 Critical Patch Update. Customers should obtain and install the appropriate security update for their supported Simphony deployment through My Oracle Support.

### Recommended Actions:
Until patching is complete, organizations can restrict access to the EGateway Printing Handler and Kiosk administrative interfaces to trusted systems and network segments. Prevent direct internet access to Simphony administrative services and restrict or block outbound SMB (TCP 445) from Simphony hosts wherever operationally feasible. These measures may reduce exposure but do not eliminate the underlying vulnerabilities.

For more details, you can read the complete article here: [Read full article](https://horizon3.ai/attack-research/vulnerabilities/oracle-hospitality-simphony-vulnerabilities/)