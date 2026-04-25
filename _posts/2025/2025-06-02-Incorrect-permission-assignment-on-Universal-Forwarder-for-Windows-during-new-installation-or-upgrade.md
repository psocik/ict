---
title: Incorrect permission assignment on Universal Forwarder for Windows during new installation or upgrade
date: 2025-06-02
categories: [VULNERABILITY]
tags: [CVE-2025-20298,SVD-2025-0602,HIGH,SPLUNK]
---

**Source:** Splunk  
**Advisory ID:** SVD-2025-0602  
**CVE ID:** CVE-2025-20298  
  
**Description:**  
In Universal Forwarder for Windows versions below 9.4.2, 9.3.4, 9.2.6, and 9.1.9, a new installation of or an upgrade to an affected version can result in incorrect permissions assignment in the Universal Forwarder Installation directory (by default, C:\Program Files\SplunkUniversalForwarder). This lets non-administrator users on the machine access the directory and all its contents.  
  
To read the complete article see: [https://advisory.splunk.com/advisories/SVD-2025-0602](https://advisory.splunk.com/advisories/SVD-2025-0602)  

**CVSSv3.1 Score:** 8.0, High  
**CVSSv3.1 Vector:** CVSS:3.1/AV:N/AC:L/PR:L/UI:R/S:U/C:H/I:H/A:H  
**CWE:** CWE-732  
**Bug ID:** VULN-27637  

---