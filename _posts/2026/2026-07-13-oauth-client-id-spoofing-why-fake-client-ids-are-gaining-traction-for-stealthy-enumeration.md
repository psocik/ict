---
title: OAuth Client ID Spoofing Why Fake Client IDs Are Gaining Traction for Stealthy Enumeration
date: 2026-07-13
categories: [CYBERSECURITY]
tags: [OAUTH,SPOOFING,CYBERSECURITY,ENUMERATION]
---

## OAuth Client ID Spoofing: Why Fake Client IDs Are Gaining Traction for Stealthy Enumeration

🚀 **Introduction**  
Proofpoint has observed OAuth client ID spoofing emerging as a novel technique, increasingly leveraged in cloud campaigns. Microsoft Entra ID returns different responses depending on whether a supplied OAuth client ID is valid and whether it corresponds to a registered application. This behavior enables account enumeration without a registered OAuth application and allows attackers to infer password validity or account state without generating a successful sign-in event.

🔍 **Research Findings**  
Researchers observed multiple campaigns at scale abusing spoofed OAuth application identifiers, with distinct tooling, infrastructure, and execution patterns indicating independent adoption by multiple threat actors. Proofpoint researchers have identified multiple campaigns where attackers extend this evasive tradecraft by spoofing the OAuth client ID (application ID), a globally unique identifier (GUID) assigned to applications.

📊 **Mechanism of Attack**  
The identifier is passed as `client_id` in authentication requests and recorded as the application ID in Entra sign-in logs. Spoofed client IDs enable account enumeration without a registered OAuth application and allow attackers to infer both password and account validity without generating a successful sign-in event. Client ID spoofing was performed by issuing POST requests to Microsoft's OAuth 2.0 token endpoint (`/common/oauth2/token`) using the Resource Owner Password Credentials (ROPC) flow, which allows direct submission of username and password credentials.

⚠️ **Error Codes and Implications**  
The resulting AADSTS error codes allow unauthenticated requestors to infer the validity of usernames and passwords, as well as the enforcement of controls such as multi-factor authentication (MFA) or Conditional Access (CA). When the supplied `client_id` is syntactically valid but does not correspond to a real application, only the application ID is recorded in the sign-in log, without a corresponding application name. The response can be used to infer whether the account exists and whether the password is correct without a registered application.

🔒 **Detection and Prevention**  
To detect similar activity, defenders should monitor sign-in logs for events without an application name, which may indicate spoofed client IDs. This means that detections that look for surges against a specific application name may miss this activity entirely, as the field is blank. Even when enumeration is detected, defenders may not realize that valid credentials were identified and may overlook compromised credentials entirely.

For more detailed insights, you can read the complete article here: [Read full article](https://www.proofpoint.com/us/blog/threat-insight/oauth-client-id-spoofing-why-fake-client-ids-are-gaining-traction-stealthy)