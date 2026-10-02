---
title: Hallucinating Credibility China-Aligned TA419 Impersonates its Way into US AI Policy Circles
date: 2026-10-01
categories: [CYBERSECURITY]
tags: [CHINA,TA419,AI,PHISHING,CYBERSECURITY]
---

## Hallucinating Credibility: China-Aligned TA419 Impersonates its Way into US AI Policy Circles

In July 2026, a China-aligned threat actor known as TA419 conducted multiple credential phishing campaigns, impersonating prominent economists and artificial intelligence (AI) policymakers. This included targeting a former member of the White House Office of Science and Technology Policy leadership team, aiming at AI experts working for US think tanks, universities, and legal sector organizations. 

TA419 previously impersonated a notable employee from Anthropic to target an AI policy expert at a US think tank in February 2026. This activity likely supports broader Chinese intelligence objectives to gain insights into ongoing developments within the US AI policy and regulatory landscape. This comes amid intense strategic competition, accusations of model distillation, and export controls involving the US and China. 

### Phishing Campaigns

Since at least April 2025, TA419 has been observed conducting regular targeted credential phishing campaigns against individuals working for US- and Japan-based think tanks, defense contractors, universities, and law firms. The group initially sent benign conversation starter emails, themed around AI policy, to build rapport and solicit responses from targets. Once a target replied, TA419 followed up with a multi-stage URL redirection chain leading to an Adversary-in-the-Middle (AitM) credential phishing page. 

Beginning on July 8, 2026, TA419 impersonated Lynne Edwards Parker, the former Principal Deputy Director of the White House Office of Science and Technology Policy, and later Heidi Crebo-Rediker, a prominent economist and foreign policy expert. These campaigns targeted AI policy experts at US think tanks, universities, and law firms. 

### Technical Details

TA419 uses URL shortener services to redirect targets to a series of actor-controlled domains. The first domain serves as an initial filter, conducting a Cloudflare Turnstile check behind a fake OneDrive loading screen before redirecting to an AitM credential phishing page. Both July 2026 campaigns targeting US AI policy experts utilized the same first-stage and second-stage domains. 

The AitM phishing chain targets Microsoft 365 / Entra ID through the OfficeHome application and is built on Frameless BitB, an open-source Browser-in-the-Browser kit. TA419 has extended this kit with a custom telemetry and automation module that tracks the target's progress through the Microsoft sign-in flow, including multi-factor authentication (MFA). 

Organizations in the scope of TA419 activity should consider phishing-resistant, origin-bound authentication such as passkeys. Individual targets should treat unsolicited subject-matter outreach as a plausible pretext stage and verify the legitimacy of unexpected communications via another independent medium.

[Read full article](https://www.proofpoint.com/us/blog/threat-insight/hallucinating-credibility-china-aligned-ta419-impersonates-its-way-us-ai-policy)