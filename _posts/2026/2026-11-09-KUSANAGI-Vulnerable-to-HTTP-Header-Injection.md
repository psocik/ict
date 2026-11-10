---
title: KUSANAGI Vulnerable to HTTP Header Injection
date: 2026-11-09
categories: [SECURITY]
tags: [KUSANAGI,HTTP,VULNERABILITY,SECURITY,NGINX]
---

## KUSANAGI Vulnerable to HTTP Header Injection 🚨

KUSANAGI, provided by GMO Prime Strategy Co., Ltd., has been found to contain an **HTTP header injection vulnerability** affecting multiple versions. The vulnerable versions include:

- **KUSANAGI 7**
- **KUSANAGI 8**
- **KUSANAGI 9**

Specifically, the Security / Enterprise Edition versions **10.7.2-1 and earlier**, as well as Free / Business / Premium Edition versions **9.12.2-1 and earlier**, are impacted.

### Vulnerability Details 🔍

This vulnerability, tracked as **CVE-2026-117477**, falls under the category of **Improper Neutralization of CRLF Sequences in HTTP Headers (CWE-113)**. It is present in a redirect rule included in the Nginx configuration for WordPress. The vulnerability has been assigned a **CVSS 4.0 Base Score of 5.1** and a **CVSS 3.1 Base Score of 6.1**.

### Impact ⚠️

The impact of this vulnerability allows for arbitrary headers to be injected into the HTTP response when a user accesses a specially crafted URL. 

### Recommended Actions 🛠️

To mitigate this issue, users should:
- Update the software to the latest version as advised by the developer.
- If an update is not possible, implement mitigation measures as per the developer's guidance.

GMO Prime Strategy Co., Ltd. has reported this vulnerability to **JPCERT/CC** to inform users of the necessary solutions through **JVN**. This coordinated disclosure highlights the collaboration between GMO Prime Strategy Co., Ltd. and JPCERT/CC under the **Information Security Early Warning Partnership**.

For more details, you can read the complete article here: [Read full article](https://jvn.jp/en/vu/JVNVU92635551/) 
