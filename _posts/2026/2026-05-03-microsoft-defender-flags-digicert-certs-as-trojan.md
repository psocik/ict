---
title: Microsoft Defender Flags DigiCert Certs as Trojan
date: 2026-05-03
categories: [SECURITY]
tags: [MICROSOFT,DIGICERT,SECURITY,TROJAN,MALWARE]
---

## Microsoft Defender Flags DigiCert Certs as Trojan 🚨

Microsoft Defender is mistakenly identifying legitimate DigiCert root certificates as **Trojan:Win32/Cerdigent.A!dha**, leading to widespread false-positive alerts. In some instances, these certificates are being removed from Windows systems. 

According to cybersecurity expert **Florian Roth**, this issue arose after Microsoft included the detections in a Defender signature update on **April 30th**. Administrators globally have reported that DigiCert root certificate entries are being flagged as malware and subsequently removed from the Windows trust store.

The affected certificates include:
- 0563B8630D62D75ABBC8AB1E4BDFB5A899B24D43
- DDFB16CD4931C973A2037D3FC83A4D7D775D05E4

On impacted systems, these certificates were removed from the AuthRoot store under the Registry key: `HKLM\SOFTWARE\Microsoft\SystemCertificates\AuthRoot\Certificates\`. Microsoft has since addressed the detections in Security Intelligence update version **1.449.430.0**, with the latest update now being **1.449.431.0**. Reports indicate that this fix also restores previously removed certificates.

These false positives come shortly after a disclosed DigiCert security incident that allowed threat actors to acquire valid code-signing certificates used for malware. DigiCert's incident report explains that a malware incident targeted a customer support team member, and upon detection, the threat vector was contained. 

DigiCert has revoked **60 code-signing certificates**, including **27** linked to a **"Zhong Stealer"** malware campaign. This aligns with earlier reports from security researchers who observed newly issued DigiCert EV certificates being misused in malware campaigns. 

The malware, referred to as **"Zhong Stealer"**, appears to function more like a remote access trojan (RAT) than a traditional infostealer. It was distributed through phishing emails containing a fake image or screenshot, leading to a decoy executable that retrieves a second-stage payload from cloud storage.

While Microsoft has not confirmed that the Defender detections are directly related to the DigiCert incident, the timing and focus on DigiCert-related certificates suggest a possible connection. However, it is important to note that the certificates flagged by Microsoft Defender are root certificates in the Windows trust store and do not match the revoked DigiCert code-signing certificates used for malware.

For more details, [Read full article](https://www.bleepingcomputer.com/news/security/microsoft-defender-wrongly-flags-digicert-certs-as-trojan-win32-cerdigentadha/)