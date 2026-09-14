---
title: Critical Dell ObjectScale Vulnerabilities Allow Malicious Users to Compromise the Affected System
date: 2026-09-13
categories: [CYBERSECURITY]
tags: [DELL,OBJECTSCALE,VULNERABILITIES,CYBERSECURITY,SECURITY]
---

## Critical Dell ObjectScale Vulnerabilities 🚨

Dell Technologies has released a security advisory regarding multiple vulnerabilities affecting **Dell ObjectScale** and **Elastic Cloud Storage (ECS)** deployments. Among these, a critical remote code execution flaw could allow an unauthenticated attacker to compromise vulnerable systems. The advisory, tracked as **DSA-2026-393**, was published on **September 10, 2026**.

### Key Vulnerabilities:
- **CVE-2026-70416**: A critical untrusted-data deserialization vulnerability in Dell ObjectScale versions earlier than **4.4.0.0**. This flaw carries a **CVSS score of 10.0** and could enable an unauthenticated remote attacker to execute code on an affected system. Successful exploitation could grant an attacker control over the ObjectScale environment, allowing access to data, configuration alterations, disruption of storage operations, deployment of malicious payloads, or establishment of persistence in the affected infrastructure.

- **CVE-2025-43936**: An improper authentication vulnerability rated **8.1**. This flaw affects ObjectScale versions before **4.4.0.0** and may allow an unauthenticated attacker with remote access to gain unauthorized access. Although its attack complexity is rated high, it does not require credentials or user interaction, emphasizing the need to limit network exposure while updates are deployed.

- **CVE-2026-26947**: An improper privilege management flaw with a **CVSS score of 6.7**. A local attacker with high privileges could exploit it to elevate privileges further, affecting confidentiality, integrity, and availability.

- **CVE-2025-36591**: A broken or risky cryptographic algorithm vulnerability rated **4.4**. A high-privileged local attacker could potentially exploit this issue to expose sensitive information.

- **CVE-2026-76104**: An incorrect permission assignment vulnerability in the operating system with a **CVSS score of 5.5**, which could allow a high-privileged remote attacker to cause denial-of-service conditions.

Additionally, the advisory lists third-party component vulnerabilities involving **Apache Log4j**, **liblzma**, and the **Linux kernel**.

### Recommendations:
Dell recommends that customers upgrade affected ObjectScale and ECS systems to version **4.4.0.0** or later as soon as possible. Customers running supported affected releases may also upgrade directly to version **4.2.0.1**. Organizations should open an Operating Environment Upgrade service request and reference **DSA-2026-393**. Until updates are applied, Dell advises using the **Secure Service-Level Communication** guidance in the official Security Configuration Guide to mitigate **CVE-2025-43936**. Security teams should restrict administrative and storage-management interfaces to trusted networks, review exposed ObjectScale services, monitor for abnormal authentication activity, and investigate unexpected configuration or permission changes.

Dell credited security researcher **WinD39**, also known as **Huynh Dinh Vu**, for reporting **CVE-2026-70416**.

For more details, [Read full article](https://cybersecuritynews.com/dell-objectscale-vulnerabilities/).