---
title: ShinyHunters 'does not like Salesforce at all,' claims the crew accessed Gainsight 3 months ago
date: 2025-11-21
categories: [SECURITY]
tags: [CYBERSECURITY,DATA BREACH,SALESFORCE,GAINSIGHT]
---

The ShinyHunters cybercrime group has claimed responsibility for the Gainsight breach, asserting they leveraged access gained during the earlier Salesloft Drift hack to pilfer data from hundreds of Salesforce customers. A member of the group told The Register they had access to Gainsight for nearly three months.

The gang indicated the Salesloft Drift breach provided entry points into numerous, lucrative systems. The initial breach occurred in March when attackers compromised a Salesloft GitHub account and stole OAuth tokens from Salesloft Drift's integration with Salesforce. Drift, a sales automation application, integrates with Salesforce using connected-app APIs. By compromising these OAuth tokens, the threat actors were able to silently steal Salesforce customer data. ShinyHunters claims they also gained access to Gainsight, a customer success platform that integrates with Salesforce and other CRMs like HubSpot, as well as support tools such as Zendesk, during the Salesloft Drift breaches.

Gainsight has engaged Mandiant to assist with the ongoing investigation into a connection issue affecting Gainsight-published applications on Salesforce. Salesforce revoked all active access and refresh tokens associated with Gainsight-published applications and temporarily removed them from the AppExchange. Zendesk also revoked its connector access to Gainsight as a precaution. Similarly, the Gainsight app was temporarily removed from the HubSpot Marketplace. Google's Threat Intelligence Group believes this breach is linked to UNC6240, also known as ShinyHunters, and estimates over 200 Salesforce instances may be affected.

According to ShinyHunters, the initial access stemmed from the Salesloft GitHub account compromise, where they discovered OAuth tokens for Drift customers' technology integrations within Drift's AWS environment. These tokens were subsequently used to breach several companies' Salesforce instances and exfiltrate customer data. The group stated that Gainsight was used as a test to gauge current monitoring levels.

Salesforce reportedly detected the unauthorized activity within approximately one to two weeks after the initial intrusion. ShinyHunters claims to have contacted Salesforce, but provided no further details. The group, part of a crime collective that briefly disbanded, now claims to be back in action and is allegedly recruiting insiders at major enterprises. 

To read the complete article see: https://www.theregister.com/2025/11/21/shinyhunters_salesforce_gainsight_breach/