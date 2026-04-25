---
title: ShinyHunters Claims Rockstar Games Snowflake Breach via Anodot
date: 2026-04-11
categories: [CYBERSECURITY]
tags: [SHINYHUNTERS,ROCKSTAR,BREACH,ANODOT,CYBERSECURITY]
---

## ShinyHunters Claims Rockstar Games Snowflake Breach 🚨

Rockstar Games is back in the news because the ShinyHunters hacking group claims it accessed the company’s Snowflake environment and may be holding a large volume of data at risk of being leaked. The message, published on the group’s dark web leak site on April 11 (UK time), sets a deadline of April 14 and follows a familiar pattern of pay or face public exposure.

This case differs from a typical direct breach because the attackers pointed to Anodot, a SaaS platform used for cloud cost monitoring and analytics, as the entry point. In their post, ShinyHunters claimed, **“Rockstar Games, your Snowflake instances were compromised thanks to Anodot.com. Pay or leak. This is a final warning to reach out by 14 Apr 2026 before we leak, along with several annoying (digital) problems that’ll come your way. Make the right decision, don’t be the next headline.”**

Recent reporting confirmed that Anodot suffered a security breach, which attackers then used as a way to access customer environments connected through integrations. Reportedly, attackers were able to extract authentication tokens from Anodot, which function as trusted credentials between services. With those tokens, they could access connected Snowflake accounts without needing to exploit vulnerabilities in Snowflake itself. Once inside Snowflake environments, attackers exfiltrated data using normal database operations. Worse, because the access appeared legitimate, detection was not immediate in many cases. Several organizations were impacted before the activity was flagged and contained.

ShinyHunters has built a track record of targeting identity systems, API keys, and third-party integrations instead of relying on traditional exploits. Their focus is to gain valid access, extract large databases, and then apply pressure through public leak threats. Earlier this March, ShinyHunters said it had obtained Salesforce-linked data tied to more than 400 companies. Since then, the group has published data from 26 of those organizations, giving weight to at least part of its claims. Some of the claimed and confirmed cases linked to ShinyHunters include the following organizations: Cisco, Ben.nl, Odido NL, Telecom Giant Telus, Dutch Telecom Odido, European Commission, SoundCloud, Crunchbase, Betterment, and several others.

As for Rockstar Games, the company has not issued a statement addressing the claim. What the Anodot incident shows is that while automation and cloud integrations improve efficiency, they can also introduce serious data security risks when access controls or tokens are exposed.

[Read full article](https://hackread.com/shinyhunters-rockstar-games-snowflake-breach-anodot/)