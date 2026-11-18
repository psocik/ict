---
title: OPTIMJACK When Trusted JavaScript Becomes a Supply Chain Attack
date: 2026-11-17
categories: [CYBERSECURITY]
tags: [MALWARE,JAVASCRIPT,SUPPLY_CHAIN_ATTACK,OPTIMIZELY]
---

## OPTIMJACK: When Trusted JavaScript Becomes a Supply Chain Attack

On **November 16, 2026**, attackers exploited a vulnerability in Optimizely's Web Experimentation platform to inject malicious JavaScript into customer projects. Report URI researcher **Scott Helme** identified **188 infected snippets** associated with **178 organizations**, including **Zoom**, **CNN**, **Salesforce**, **GitLab**, **IKEA**, and **HSBC**. The attackers did not need to modify those organizations' application source code or compromise their web servers. Instead, the malicious code was delivered through Optimizely snippets that affected websites already trusted.

### Impact of the Attack
The payload could:
- Replace cryptocurrency wallet addresses
- Capture payment-card details entered into affected first-party forms
- Collect non-HttpOnly cookies and page screenshots
- Attempt to deliver exploit kits to some iPhone and iPad users

The campaign, named **OPTIMJACK** by independent researcher **Amirul Cyber**, highlights how a compromise of a trusted software provider can turn a routine third-party integration into a malware delivery channel. For organizations relying on third-party applications, JavaScript libraries, analytics platforms, and cloud services, this incident raises a fundamental question: **how can enterprises trust software whose code can change after it has been approved?**

### Details of the Exploit
Optimizely Web Experimentation allows organizations to run A/B tests and personalize website experiences by loading JavaScript snippets associated with customer projects. According to Report URI, the attacker inserted a small JavaScript loader into the Project JavaScript configuration of affected projects, leaving the rest of each snippet largely intact. The modified files continued to be served through Optimizely's delivery infrastructure, meaning the browser received malicious code from a source the affected websites were already configured to trust.

Report URI documented several loader variations. One loaded a remote payload from **1688360[REDACTED BY DNB EDITORS TO GET PAST GOOGLE FILTERS]**. Smartsheet's snippet was cleaned and then reinfected, indicating that the attacker still had the ability to modify that project during the cleanup effort. Some affected customers served their Optimizely snippets from their own domains rather than directly from **cdn.optimizely.com**. As a result, hunting only for requests to **cdn.optimizely.com** would miss some affected implementations; investigations should identify the Optimizely project snippets in use, including customer-hosted copies.

### Response from Optimizely
Optimizely's status-page notice states that an unauthorized party "exploited a vulnerability in Experimentation," and that the company has "fixed the vulnerability" and removed the injected code from affected projects. However, the public reporting does not clarify how the attacker obtained write access to so many unrelated customer projects. This question remains unanswered in the available public evidence. The Optimizely-specific injection was first observed on **November 16**, at **04:21 UTC** in a BBC snippet, according to the timeline reported by Scott Helme. Report URI tracked cleanup throughout that same day: by **21:52 UTC**, only one of the **188 infected snippets** it had identified still contained the code. StepSecurity estimates that most sites were exposed for about **16 hours**.

For more details, check out the full article: [Read full article](https://www.reversinglabs.com/blog/optimjack-when-trusted-javascript-becomes-a-supply-chain-attack)