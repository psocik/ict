---
title: Microsoft Entra ID flaw allowed hijacking any company's tenant
date: 2025-09-22
categories: [SECURITY]
tags: [MICROSOFT,ENTRA ID,SECURITY,HIJACKING,VULNERABILITY]
---

Security researcher Dirk-jan Mollema, founder of offensive security Outsider Security, discovered a token validation flaw that gave him Global Admin privileges in every Entra ID tenant.

This level of access allows full tenant compromise and opens the door to any service authenticated through Entra ID.

Mollema says that “this whole Actor token design is something that never should have existed,” because they lack the proper required security controls:

- There are no logs when Actor tokens are issued.
- Since these services can craft the unsigned impersonation tokens without talking to Entra ID, there are also no logs when they are created or used.
- They cannot be revoked within their 24-hour validity.
- They completely bypass any restrictions configured in Conditional Access.
- We have to rely on logging from the resource provider to even know these tokens were used in the tenant.

To read the complete article see: [Bleeping Computer](https://www.bleepingcomputer.com/news/security/microsoft-entra-id-flaw-allowed-hijacking-any-companys-tenant/).