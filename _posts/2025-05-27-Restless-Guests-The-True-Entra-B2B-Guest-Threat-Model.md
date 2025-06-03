---
title: Restless Guests The True Entra B2B Guest Threat Model
date: 2025-05-27
categories: [RESEARCH]
tags: [Entra,B2B,Guest Threat,Microsoft,Access Control]
---

The Entra Access Flaw Hiding in Plain Sight

Inviting external guest users is a common and useful practice for collaboration with external partners. These guest accounts are typically assigned limited privileges to reduce risk in the event they become compromised, but they exist outside of your organization's controls. This guest behavior may surprise Azure administrators because typical threat models and best practices don’t account for an unprivileged guest creating their own subscription within your tenant.

In this blog, we’ll break down how little-known Microsoft Billing permissions can be misused by Entra guest users to create subscriptions in external tenants where they hold no direct privileges. You’ll learn how attackers can exploit this unexpected access to achieve unauthorized reconnaissance and persistence in the defender’s Entra ID. We also detail how some of these methods could lead to further privilege escalation in certain scenarios. We’ll walk through real-world abuse paths, explore why this gap in access control is so dangerous, and outline what defenders need to know now.

In other words, the guest you invited could quickly overstay their welcome.

To read the complete article see:

[Restless Guests](https://www.beyondtrust.com/blog/entry/restless-guests) 

***

***Working at Team Cymru is more than a job — it’s a chance to be part of something meaningful. Enjoy outstanding benefits, work with incredible people, and contribute to a mission that truly matters. Explore open roles and join us: [Team Cymru Careers](https://www.team-cymru.com/careers)