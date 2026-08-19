---
title: NASA Ground Control Software Flaw Enables Unauthenticated Commands
date: 2026-08-18
categories: [CYBERSECURITY]
tags: [NASA,VULNERABILITY,SECURITY,SOFTWARE]
---

## 🚨 Critical Vulnerability in NASA's Ground Control Software

A significant vulnerability has been discovered in NASA's open-source AMMOS Instrument Toolkit (AIT)-GUI ground software. This flaw could allow **unauthenticated attackers** to issue commands to spacecraft and instruments, execute server-side scripts, and run command sequences. AIT-GUI serves as the browser-based operator console for NASA's AMMOS Instrument Toolkit, designed for ground data systems to communicate with instruments and spacecraft.

The flaw is tracked as **GHSA-p9r8-2q67-fp86** and has been assigned a **CVSS rating of 9.4**. It specifically affects AIT-GUI versions through 2.5.1, and no CVE had been assigned at the time of writing. The issue was disclosed by Cycode researcher **Yuval Elbar** on August 18, and it has since been fixed in AIT-GUI version 2.5.2.

### 🛠️ Technical Details

AIT-GUI starts its web server on all network interfaces instead of adhering to its configured host setting. Additionally, the API lacks authentication, authorization, or cross-site request forgery (CSRF) protection on state-changing endpoints. The `/cmd` route can relay commands to the command bus, while `/script/run` and `/seq` can execute scripts and command sequences. This poses a significant risk as these web functions sit between an operator console and command infrastructure.

### ⚠️ Attack Vector

The attack does not require direct network access to the AIT-GUI server. The report indicates that state-changing routes accept browser-compatible form submissions without CSRF protection, allowing a malicious website visited by an operator to send requests to the service. Cycode demonstrated that an operator accessing a host-local or firewalled deployment could be targeted through their browser, with cross-origin requests delivered without a CORS preflight.

### 🔒 Recommendations

To mitigate these risks, the project recommends:
- Implementing authentication and authorization for state-changing endpoints
- Adding CSRF protection
- Binding the server to its configured host
- Ensuring path confinement for the affected routes

For more details, you can read the complete article [here](https://www.infosecurity-magazine.com/news/nasa-ground-control-software-flaw/).