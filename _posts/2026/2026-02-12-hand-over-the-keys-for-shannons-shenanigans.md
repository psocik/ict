---
title: Hand Over the Keys for Shannon’s Shenanigans
date: 2026-02-12
categories: [CYBERSECURITY]
tags: [CYBERSECURITY,AI,LINUX,THREATS]
---

## New Threat Actor Uncovered 🚨

CISCO Talos has uncovered a new threat actor, **UAT-9921**, using the advanced **VoidLink** framework to target mainly Linux systems. VoidLink stands out for its modular, on-demand plugin creation, auditability, and ability to evade detection, with features rarely seen in similar threats. 

UAT-9921 has been active since at least 2019, focusing on the technology and financial sectors, and uses advanced techniques for both compromise and stealth. VoidLink introduces powerful new methods for attackers to compromise, control, and hide within Linux environments, which are common in critical infrastructure and cloud services. Its ability to quickly generate customized attack tools and evade detection makes it harder for defenders to respond. The framework's advanced stealth and lateral movement features increase the risk of undetected breaches and data theft. 

### Strengthen Your Defenses 🔒

Update your defenses and use the Snort rules and ClamAV signature mentioned in the blog to help detect and block VoidLink activity. Strengthen Linux security, especially for cloud and IoT environments, and monitor for unusual network activity or signs of lateral movement. Make sure endpoint detection solutions are up to date and configured to recognize the latest threats. 

### AI in Cybersecurity 🤖

In other intelligence, last week, yet another security AI tool made the rounds on social media: **Shannon**, a fully autonomous AI penetration testing tool created by Keygraph. It “autonomously hunts for attack vectors in your code, then uses its built-in browser to execute real exploits, such as injection attacks, and auth bypass, to prove the vulnerability is actually exploitable.” Shannon requires access to the application’s source code, repository layout, and AI API keys. 

Even as a cybersecurity novice, I know that this in itself is a major liability that organizations should investigate and weigh carefully before proceeding. Quoting Joe, "As disciples of security, we understand installing first and asking questions later is practically asking to get pwnt." Relying on access to source code widens the gap between simulated and real-world attacks. 

### Other Security Headlines 📰

AI-powered pentesters aren’t going away any time soon. Anthropic’s Claude Opus 4.6 was also released last week. Unlike Shannon, they added a new layer of detection to support their team in identifying and responding to Claude cyber misuse. 

In other top security headlines, **SolarWinds WHD attacks** highlight risks of exposed apps, with several vendors in recent days warning of exploitation of vulnerabilities in WHD. **Ivanti EPMM** exploitation is widespread as governments and others are targeted; Ivanti released advisories on Jan. 29 for code injection vulnerabilities in the on-premises version of Endpoint Manager Mobile. Researchers warn the activity shows evidence of initial access brokers preparing for future attacks. 

A new **“ZeroDayRAT” spyware kit** enables total compromise of iOS and Android devices, with capabilities including victim and device profiling, including model, OS, country, lock status, SIM and carrier info, dual SIM phone numbers, app usage broken down by time, preview of recent SMS messages, and more. 

Finally, the **European Commission** probes intrusion into staff mobile management backend, potentially giving intruders a peek inside the official phones carried by EU staff. 

For more details, [Read full article](https://blog.talosintelligence.com/hand-over-the-keys-for-shannons-shenanigans/)