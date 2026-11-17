---
title: AI-Written Patches Becoming Attack Maps for Hackers
date: 2026-11-16
categories: [CYBERSECURITY]
tags: [AI,PATCHES,SECURITY,VULNERABILITIES,HACKERS]
---

## AI-Written Patches Becoming Attack Maps for Hackers

This summer, the maintainers of **vm2**, an open-source JavaScript sandboxing library, shipped fixes for **34 separate sandbox-escape vulnerabilities**, and Anthropic's Claude co-wrote **19 of them**. Weeks later, a security researcher pointed an AI agent at one of the advisories and asked for a way around the patch. The agent delivered. With published CVEs higher than ever due to AI assistance, the patches for these flaws can serve as blueprints for attackers, Nejad warned. Rubrik's experience reflects a broader asymmetry that other researchers have observed in recent months: AI models have become very good at offense -- finding vulnerabilities and building exploits -- while their defensive skills, such as writing secure code and correct patches, have lagged behind.  

More recently, in a benchmark test called **P2Patch**, researchers pitted two AI agents against each other: one wrote exploits for **101 real vulnerabilities**, and the other patched the code until the exploits stopped working. Then the first agent attacked the patched programs again, looking for a different way to trigger the same flaw. In **41 of the 101 cases**, it succeeded.  

The issue is not that AI always writes worse patches than humans, but that the rate of vulnerability discovery is now so fast that humans alone can't keep up. This is combined with the offensive capabilities of AI agents that enable attackers to analyze and reverse engineer patches at machine speed. "Progress on software security used to be limited by how quickly we could find new vulnerabilities," Anthropic wrote in its initial Glasswing update. "Now it's limited by how quickly we can verify, disclose, and patch the large numbers of vulnerabilities found by AI." In June, the Forum of Incident Response and Security Teams (FIRST) projected around **66,000 CVE assignments** for this year. With two months left, the number is already approaching **100,000**.  

If AI agents are scouring code repositories for vulnerability variants, one might be inclined to think that closed-source software, where the patch is usually inside a compiled binary, is safer. That's not necessarily the case given that AI models are now also great at reverse engineering. In June, when Anthropic's researchers tested what an attacker can do with AI-assisted patch diffing, they gave a model nothing beyond what's public on patch day. It produced a working exploit within an hour of a Firefox fix landing. Last month, the Microsoft Edge Security team warned that attackers are increasingly taking advantage of the time gap between when information about a potential vulnerability becomes available in a code commit or test release in one project and when the patch trickles down to other projects. "This is patch-gap abuse," the Edge team said. "AI-assisted analysis and exploit development could compress work that once took weeks into hours."  

[Read full article](https://www.csoonline.com/article/4248687/ai-written-patches-are-becoming-attack-maps-for-hackers.html)