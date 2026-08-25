---
title: A Social Engineering Attempt Against ReliaQuest What We Found
date: 2026-08-23
categories: [CYBERSECURITY]
tags: [SOCIAL ENGINEERING,RELIAQUEST,CYBER ATTACK,SECURITY]
---

## A Social Engineering Attempt Against ReliaQuest: What We Found

On August 22, 2026, ReliaQuest was the target of a social engineering attack. While unsuccessful beyond temporarily exposing one identity, the attempt was an important reminder of the persistent tactics of threat actor groups. ReliaQuest is sharing the full details of this attempt for transparency and so others can learn from this playbook. 🚀

The threat actor registered a lookalike domain and stood up a fake ReliaQuest single sign-on (SSO) page behind a content delivery network. The threat actor then called multiple ReliaQuest teammates, each time posing as a security employee by name in an attempt to steer them towards the fake page. One teammate entered their password and approved the push notification on their phone, which handed the attacker a brief session on our identity dashboard.

The extent of the access was view-only. No ReliaQuest applications or systems were accessed, and no customer data was ever touched. The threat actor continued with attempts to access these applications from the dashboard but was consistently denied due to the security controls in place. Our investigation has found the following: the threat actor obtained a single identity session with view-only access to our identity dashboard before access was terminated. No additional identities were accessed, no business applications were reached, no customer or ReliaQuest data was accessed beyond the user's login credentials, and no persistence was established. Claims that ReliaQuest was compromised or targeted by ransomware are false. ❌

Our defense in depth starts from the assumption that a threat actor will eventually phish someone's account. Our controls include device trust which prevent non-ReliaQuest devices from accessing any application or systems and containment actions terminated the attacker's sessions, expired the password, and reset every authentication factor. This playbook is consistent with what we are seeing across the industry: an impersonation call, a throwaway lookalike domain registered and burned within the hour, a harvesting page behind a content delivery network, MFA push abuse, and a rapid attempt to enroll a new authenticator. 🔒

[Read full article](https://reliaquest.com/blog/threat-spotlight-social-engineering-attempt-against-reliaquest-what-we-found/)