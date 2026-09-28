---
title: Zero-Click Vulnerabilities in Salesforce Agentforce Expose Wider AI Agent Risk
date: 2026-09-25
categories: [SECURITY]
tags: [SALESFORCE,AI,VULNERABILITIES,SECURITY,DATA-EXFILTRATION]
---

## Zero-Click Vulnerabilities in Salesforce Agentforce Expose Wider AI Agent Risk

Security researchers at Zenity Labs have disclosed a set of **zero-click vulnerabilities** in Salesforce Agentforce that allowed attackers to silently exfiltrate sensitive data related to customer relationship management (CRM) without any interaction from the victim and without the attacker ever authenticating into the target's Salesforce environment. The findings, published on **September 24** by Zenity's threat research team, detail an attack chain dubbed **'SalesBleed.'**

According to the report, attackers could plant hidden prompt injection payloads inside public-facing Web-to-Lead forms, a standard Salesforce feature that allows external users to submit data that flows directly into CRM records. When an Agentforce agent later processed that record as part of normal business operations, the embedded instructions would hijack the agent's behavior. 🚨

Critically, the attacker could perform a successful compromise without direct access to the target organization, and the attack required no click or credential theft. The lead submission alone was enough to seed the payload, and normal agent operation did the rest.

### Attack Chain Elements
The attack chain combined three elements:
- **Prompt injection** via Web-to-Lead forms providing the agent with the ability to ingest untrusted external input;
- The agent trusting record content as instructions, allowing it to render links or images back to a user interface;
- The agent's underlying access to sensitive tool and data permissions.

Once triggered, the injected payload could instruct the agent to quietly query and exfiltrate sensitive account data, including company names, deal sizes, and other CRM fields, using **DNS-based exfiltration techniques** that evaded Salesforce's Trusted URLs redaction controls, a safeguard designed to prevent exactly this kind of data leakage through outbound links. 🔒

Zenity reported the vulnerabilities to Salesforce in June, and Salesforce fully fixed the URL redaction bypass, which remediated the issues, on **August 18**. While the specific vulnerabilities in SalesBleed have been fixed, the Zenity researchers emphasized that the underlying risk pattern is not unique to Agentforce. Any AI agent that reads or processes records submitted by external, untrusted sources, renders links, images, or other rich content back to users, and holds tool access to sensitive backend data "has the same three ingredients sitting in the same place," creating a latent path for prompt injection-driven exfiltration. 

"Our payload asked for company names and deal sizes, but the injection could have asked for anything the subagent's Query Records tool can reach (which can include sensitive data). In a typical General CRM deployment, that includes accounts, contacts, and more," the Zenity report noted.

For more details, [Read full article](https://www.infosecurity-magazine.com/news/vulnerabilities-salesforce-ai/).