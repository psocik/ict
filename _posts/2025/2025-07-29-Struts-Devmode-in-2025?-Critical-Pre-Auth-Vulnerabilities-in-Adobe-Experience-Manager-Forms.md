---
title: Struts Devmode in 2025? Critical Pre-Auth Vulnerabilities in Adobe Experience Manager Forms
date: 2025-07-29
categories: [SECURITY]
tags: [ADOBE,VULNERABILITIES,AEM FORMS,STRUTS2]
---

**Vulnerabilities in AEM Forms**  
The Searchlight Cyber Research Team discovered and disclosed three critical vulnerabilities in Adobe Experience Manager Forms to Adobe in late April 2025.  
As of writing this research post, 90 days have passed since our disclosure to Adobe. During this time, Adobe has only released a patch for one of the three critical vulnerabilities, the insecure deserialization vulnerability leading to command execution (CVE-2025-49533). Their official advice for this vulnerability can be found [here](https://slcyber.io/assetnote-security-research-center/struts-devmode-in-2025-critical-pre-auth-vulnerabilities-in-adobe-experience-manager-forms).  
The remaining two vulnerabilities, including the authentication bypass to RCE chain via Struts2 devmode (SL-AEM-FORMS-1) and the XXE within AEM Forms web services (SL-AEM-FORMS-2), do not have publicly available patches or remediation advice.  
We strongly recommend restricting access to Adobe Experience Manager Forms from the external internet when deployed as a standalone application.