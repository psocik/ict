---
title: Microsoft OAuth App Impersonation Campaign Leads to MFA Phishing
date: 2025-07-31
categories: [RESEARCH]
tags: [MICROSOFT,OAUTH,PHISHING,MFA]
---

## Overview 

Proofpoint has identified a cluster of activity using Microsoft OAuth application creation and redirects that lead to malicious URLs enabling credential phishing. The fake Microsoft 365 applications impersonate various companies including RingCentral, SharePoint, Adobe, and DocuSign. Proofpoint first observed this activity in early 2025 and it remains ongoing.  

The goal of the campaigns is to use OAuth applications as a gateway lure to conduct other activities, mostly to obtain access to Microsoft 365 accounts via MFA phishing. The phishing campaigns leverage multifactor authentication (MFA) attacker-in-the-middle (AiTM) phishing kits, predominantly Tycoon. Such activity could be used for information gathering, lateral movement, follow-on malware installation, or to conduct additional phishing campaigns from compromised accounts.  

Proofpoint has observed this technique in email campaigns with over 50 impersonated applications, and multiple different phishing kits using this attack chain including Tycoon and ODx. Proofpoint threat researchers have seen a smaller number of observed applications and follow-on activity in cloud threat data. Proofpoint reported the observed apps to Microsoft.  

Notably, in June 2025, Microsoft announced it is updating default settings in Microsoft 365 by “blocking legacy authentication protocols and requiring admin consent for third-party app access. Changes start mid-July 2025 and complete by August 2025.” This update will have a positive impact on the landscape overall and will hamstring threat actors that use this technique.  

To read the complete article see: [Proofpoint Blog](https://www.proofpoint.com/us/blog/threat-insight/microsoft-oauth-app-impersonation-campaign-leads-mfa-phishing)  
