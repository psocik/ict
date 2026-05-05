---
title: The New Ouroboros Technique and How It Fits in dMSA's Security Model
date: 2026-05-04
categories: [SECURITY]
tags: [OUROBOS,DMSA,SECURITY,AUTHENTICATION]
---

## The New Ouroboros Technique and How It Fits in dMSA's Security Model

**Delegated Managed Service Accounts (dMSAs)** were designed to solve a real operational problem: moving services off legacy service accounts without breaking the environments that still depend on them. A dMSA introduces a different security model for managed service identities, shifting away from direct password retrieval and toward a **Kerberos-based authentication flow** that is intended to be more secure. 

Ouroboros is an account takeover and persistence primitive: A user with sufficient permissions over a dMSA object can gain control over the dMSA itself and over the privileges of the superseded account, and can even turn the dMSA into a way to authorize its own use. 🚀

### Group Managed Service Accounts (gMSAs)

Group Managed Service Accounts (gMSAs) are managed domain accounts with automatically generated and rotated passwords. However, the gMSA model still depended on retrieving the account's password through **Lightweight Directory Access Protocol (LDAP)**. dMSA changes that model; the Kerberos keys are not exposed through the old LDAP retrieval model. Instead, they are delivered through a Kerberos-based flow. When the account is used through the intended dMSA Kerberos flow, tied to **msDS-GroupMSAMembership**, the Key Distribution Center (KDC) can attach a **KERB-DMSA-KEY-PACKAGE** to the Ticket Granting Ticket (TGT) issued for the dMSA, providing the Kerberos material the caller needs. 

The point of dMSA is that an organization should be able to assign meaningful privileges to a managed service identity without making those privileges easy to steal. Compromising a machine using the dMSA should not automatically mean an attacker owns the identity in the same way they might with an older managed service account. 🔒

### Security Improvements

A dMSA has the **msDS-ManagedPassword** attribute with a default DENY ACE. Our testing showed that this discretionary access control list (DACL) is not the whole protection story. Even after removing that DENY ACE, an LDAP read of msDS-ManagedPassword for a dMSA still failed. We identified a specific protection in **ntdsai.dll** for LDAP reads of msDS-ManagedPassword on dMSA objects. However, we also identified another path in ntdsai.dll that can still reach the dMSA msDS-ManagedPassword attribute without the expected authorization check. This explains how a request from S-1-5-7 could still appear as a successful password fetch, as logged in older gMSA-style events. 

Ouroboros fits exactly at the boundary between using the dMSA and inheriting the superseded identity, showing how that separation can break down in practice. Control of the dMSA can be turned into a state in which operating as the dMSA is enough to inherit the superseded account's effective privileges, making the dMSA the mechanism that preserves its own successor status. 🔄

### Conclusion

dMSA looks like a meaningful security improvement, solving a real operational problem. Moving away from normal password retrieval and toward a DC-controlled Kerberos flow is a sensible change in the managed service account model. This means the security boundary has changed. The important question is no longer only whether a managed password can be read from the directory, but also whether the system correctly controls when the account can be used, and when it is allowed to inherit the value of the identity it replaced.

[Read full article](https://www.akamai.com/blog/security-research/ouroboros-technique-how-fits-dmsas-security-model)