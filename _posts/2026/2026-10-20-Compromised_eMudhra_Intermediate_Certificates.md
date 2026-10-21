---
title: Compromised eMudhra Intermediate Certificates
date: 2026-10-20
categories: [SECURITY]
tags: [EMUDHRA,CERTIFICATES,SECURITY,MOZILLA]
---

## Compromised eMudhra Intermediate Certificates

On Saturday, **October 17**, at **20:06 UTC**, Mozilla received a report from a community member that private keys associated with eight eMudhra intermediate certificates had been compromised. These keys could allow attackers to issue fraudulent HTTPS certificates for websites they do not control. At **22:59 UTC**, Mozilla completed the process of blocking the affected certificates in Firefox using OneCRL, Mozilla's centralized list of revoked certificates. OneCRL allows us to deliver this protection without requiring users to update or even restart Firefox. 🚀

Today, **October 20**, Mozilla is also releasing an update to the trusted certificates list in NSS which removes the root certificate used to sign these intermediates. Although this change is not necessary for Firefox, this helps protect other users of our trust store or third-party derivatives who do not benefit from the protection of OneCRL. This change will impact the availability of some servers for those non-Firefox users until those servers move to new certificate chains. Mozilla has since been working with the issuing CA, other root programs, and downstream trust store operators to investigate the root cause, responsibly disclose the incident, and help protect the wider ecosystem. At this time, we do not believe the issue impacts other CAs.

Mozilla recommends all trust store operators take steps to protect their users and notes specific actions. If clients will reliably check revocation information and fail-closed (reject) if it is absent, no action is needed, as the CA has marked these certificates as revoked. If the operator has a mechanism for blocking trust in particular intermediate CAs, the operator should block the certificates identified in the attached JSON impacted-intermediates.json and distribute that update to clients immediately. Otherwise, the operator should consider whether removing trust in the roots which signed these intermediates is suitable. Mozilla has done so in its latest update to NSS, and the roots which are known to chain to these certificates are listed in roots.json.

[Read full article](https://groups.google.com/a/mozilla.org/g/dev-security-policy/c/0R3XLJL6FuE)\n