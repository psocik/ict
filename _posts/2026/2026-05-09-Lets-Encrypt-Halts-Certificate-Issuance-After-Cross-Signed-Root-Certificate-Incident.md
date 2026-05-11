---
title: Let's Encrypt Halts Certificate Issuance After Cross-Signed Root Certificate Incident
date: 2026-05-09
categories: [CYBERSECURITY]
tags: [LETS-ENCRYPT,CERTIFICATE-ISSUANCE,CYBERSECURITY,INCIDENT]
---

## Let's Encrypt Halts Certificate Issuance 🚫

Let's Encrypt temporarily suspended all certificate issuance on **May 8, 2026**, after engineers identified a critical issue involving a cross-signed certificate linking the organization's Generation X root to its upcoming Generation Y root infrastructure. The incident triggered a complete shutdown of issuance across both production and staging environments before services were restored within hours. 

At **18:37 UTC** on May 8, Let's Encrypt engineers became aware of a potential incident and immediately halted all certificate issuance as a precautionary measure. The affected components included the production and staging ACME API endpoints (acme-v02.api.letsencrypt.org and acme-staging-v02.api.letsencrypt.org), as well as the production and staging portal environments hosted across two high-assurance datacenters. By **21:03 UTC**, roughly two and a half hours later, the organization confirmed that issuance had resumed.

However, as a direct result of the cross-signed certificate issue, all certificate generation was rolled back to the Generation X root. This rollback specifically impacts two ACME certificate profiles: **tlsserver** and **shortlived**. Let's Encrypt has not disclosed details about whether any incorrectly issued certificates were distributed before issuance was halted.

The timing of the incident is notable given that Let's Encrypt had already announced three significant platform changes scheduled to go live on **May 13, 2026**, just five days away. Those changes include: 
- The **tlsserver** ACME profile will begin issuing 45-day certificates as part of Let's Encrypt's phased roadmap to reduce certificate lifetimes from 90 days down to 45 days over the next two years. 
- Additionally, the **tlsclient** profile, used for TLS client authentication certificates, will be restricted exclusively to ACME accounts that have previously requested certificates from that profile. Full support for tlsclient certificates will end on **July 8, 2026**. 
- The classic ACME profile was also scheduled to transition to Generation Y intermediates, which chain to the existing X1 and X2 roots, a change designed to maintain broad compatibility across client environments.

All three changes are currently live in Let's Encrypt's staging environment and remain on track for the **May 13 production rollout**, pending resolution of the root certificate issue.

Administrators relying on automated ACME-based renewal workflows, particularly those using the **tlsserver** or **shortlived** profiles, should monitor renewal logs closely and verify that certificates issued around the May 8 window chain correctly to the expected root.

[Read full article](https://cybersecuritynews.com/lets-encrypt-halts-certificate-issuance/)