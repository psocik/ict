---
title: Actors Behind AppSuite-PDF and PDF Editor Used 26 Code-Signing Certificates to Make Software Appear Legitimate
date: 2025-09-15
categories: [CYBERSECURITY]
tags: [MALWARE,CODE-SIGNING,APPSUITE-PDF,PDF EDITOR,BAOLOADER]
---

The actors, tracked under the malware family name BaoLoader, have utilized at least 26 code-signing certificates obtained through fraudulent business registrations, primarily targeting users seeking PDF editing tools and productivity applications.

What sets this campaign apart from typical certificate abuse scenarios is the actors’ consistent pattern of obtaining multiple certificates for identical company names from different certificate authorities.

Analysis of the certificate metadata reveals consistent business serial numbers across multiple certificate authorities for identical company names. For instance, Eclipse Media Inc. certificates were issued by GlobalSign, SSL.com, Sectigo, and DigiCert, all containing matching business registration identifiers.

The malware’s persistence mechanisms include PowerShell execution designed to load Web Companion components, executing commands that bypass execution policies and load assemblies from encrypted files.

To read the complete article see: [https://cybersecuritynews.com/actors-behind-appsuite-pdf-and-pdf-editor/](https://cybersecuritynews.com/actors-behind-appsuite-pdf-and-pdf-editor/)  
