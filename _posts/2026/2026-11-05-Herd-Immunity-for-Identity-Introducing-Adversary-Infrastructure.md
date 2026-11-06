---
title: Herd Immunity for Identity Introducing Adversary Infrastructure
date: 2026-11-05
categories: [CYBERSECURITY]
tags: [ADVERSARY,INFRASTRUCTURE,IDENTITY,CYBERSECURITY,PHISHING]
---

## Herd Immunity for Identity: Introducing Adversary Infrastructure

**Source:** Huntress  
**Date Published:** November 5, 2026  

In March, our SOC observed a phishing-as-a-service operation transform Railway, a developer cloud platform with a spotless IP reputation, into a token-harvesting engine. Device code phishing lures impacted 344 organizations across five countries in under three weeks. Microsoft had no reason to classify those logins as risky. We hand-built a Conditional Access policy blocking Railway's IP ranges and deployed it to every eligible Managed ITDR tenant, successfully stopping 305 attack attempts at the door. However, the attackers quickly shifted to new infrastructure. This is the challenge we designed Adversary Infrastructure to address. It's the latest capability in Huntress Managed ITDR, evolving that one-time emergency response into continuous protection. When one tenant is targeted, every tenant benefits from the block. We refer to this as herd immunity for identity.  

The Railway campaign illustrated the current dynamics of identity attacks. Among the 344 victims, we discovered no two identical phishing lures. Each was customized enough to evade email filtering. Such variety at this scale indicates that automation or AI is generating these lures. The group behind this, EvilTokens, offers a storefront with AI workflows designed to bypass filters, personalize pretexts, and hunt inboxes for wire fraud targets. Attackers rent clean, inexpensive, trusted cloud space, establish a token relay in minutes, and dismantle it once it’s compromised. Developer platforms, VDI tunnels, and AiTM relays appear legitimate to Microsoft's risk scoring until proven otherwise. In a single 14-day window, 5,086 distinct attacker IP addresses targeted the Huntress fleet.  

Adversary Infrastructure blocks attackers at the Microsoft 365 sign-in, preventing them from ever gaining a session. When the Huntress SOC confirms the hosting, relay, or proxy infrastructure behind a compromise in one tenant, we convert it into a blocking Conditional Access policy for every eligible, opted-in tenant. Attacks from that infrastructure fail at sign-in. This entire process runs from one confirmed incident to fleet-wide blocking, often within the same day. Detection engineers validate the infrastructure, and Huntress deploys the block, rolling out one blocking policy with one named location per campaign, each labeled [HUNTRESS], to every eligible, opted-in tenant. Each block generates a Low severity incident report detailing the targeted identity, source, and campaign, and the credential the attacker attempted to use is rotated.  

Two campaigns exemplify this. LSHIY LLC involved 81 million login attempts from a single IPv6 range. Our SOC detected a password spray replaying validated credentials through ROPC, a legacy auth flow that bypasses the MFA prompt entirely. It compromised 78 accounts across 64 organizations; 55 had active Conditional Access policies requiring MFA, which did not cover the flow the attacker exploited. LSHIY is now an active Adversary Infrastructure campaign, blocking that range at sign-in. Another campaign, 1337 Services GmbH, experienced ten weeks of token replay from July to September. An attacker captured sessions through AiTM relays and replayed stolen tokens from a German hosting provider's 193.26.115[.]0/24 IP range, resulting in 497 successful sign-ins across 79 organizations. The operator cycled through six addresses in that range. Range-level blocking, maintained by Huntress and updated as the attacker evolves, is specifically designed for this pattern. In both instances, the first tenants affected bore the cleanup costs; with Adversary Infrastructure, the subsequent tenant never reaches that stage.  

Adversary Infrastructure is now live in Managed ITDR for Microsoft 365 as of today, November 5. Eligible tenants require Entra ID P1 or P2 (Business Premium, or E3 with P1, and up), Security Defaults off, and a healthy, fully onboarded tenant in Huntress.

[Read full article](https://www.huntress.com/blog/itdr-adversary-infrastructure)