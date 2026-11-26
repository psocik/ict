---
title: Autonomous Offensive Frameworks 128 AI Attacks
date: 2026-11-23
categories: [CYBERSECURITY]
tags: [AI,CYBERSECURITY,ATTACKS,INFRASTRUCTURE]
---

## Autonomous Offensive Frameworks: 128 AI Attacks 🚀

Infrawatch has conducted a thorough analysis of operational evidence from **128 AI-assisted intrusions**, tracking **10,848 services** across **8,105 hosts** running Autonomous Offensive Frameworks (AOFs). This research establishes a baseline across the wider ecosystem, revealing how these frameworks operate, how attackers deploy them, and where defenders can intervene.

Infrawatch observed more than **130 variants of ARTEX** in the wild, with ARTEX being the most-used AOF. The number of ARTEX servers rose sharply in early November, following a surge in intrusions during October. On **November 6**, Infrawatch was tracking **3.2K servers** running AOFs, which increased to **8.1K by November 24**. More servers appeared in November than in September and October combined.

Where Infrawatch could identify who was at the keyboard, the agent ran over **70% of intrusions**, either supervised or fully autonomous. Fully autonomous attacks were observed to succeed more often than those managed by a human. AOFs are fast but not proficient; the typical attack lasted **four days**, with many beginning and ending the same day. Out of these, **22 succeeded** and **23 failed**, often due to model hallucinations. **DeepSeek** and **Claude** are the most popular models used by AOFs.

AOFs operate in teams: a lead agent tasks a reconnaissance agent to profile the target's network edge, assigns hunters to different classes of vulnerability, and then a second team confirms the findings.

Attacks leverage pre-existing vulnerabilities and control failures. What has changed is not the nature of the attack; AOFs offer speed and scale. None of the successful attacks used novel tradecraft. For instance, a database with no password became the entry point into an internal network. Three were SQL injection attacks, a weakness older than most of the people (and all of the agents) exploiting it. What a skilled person could breach in a week, an agent now breaches in an afternoon. One agent created a super-administrator account at a cryptocurrency exchange and pulled **21.7K user records**, the exchange's wallet statistics, and **7.6K transaction records**.

In **45% of intrusions**, exit traffic came straight from the AOF's own server. Actors who rerouted traffic built their own proxies and VPNs, also utilizing commercial VPNs or residential proxy networks. A significant portion of the intrusions concealed the route to their AI provider, likely due to cost and model acquisition. A blocked server is easy to replace, but a banned AI subscription is not. In at least **24 attacks**, the target was someone else's AI infrastructure. One actor built a tool to mass-exploit AI coding-agent services left open on the internet, using each service's control interface to redirect the agent to a fake LLM on the actor's server.

Crucially, the infrastructure behind these attacks remains observable and blockable. Our findings demonstrate that defenders can disrupt a substantial proportion of AI-assisted intrusions by identifying and blocking the infrastructure used to launch them. Infrawatch recommends a risk-based approach tailored to an organization’s threat model, incorporating multiple infrastructure signals. This is based on real-life intrusions detailed in this blog post, not arbitrary file-hunting patterns or hashes.

Defensive measures include focusing on AOF framework hosts, which are directly associated with AOF activity, including attacker-controlled servers. It is also recommended to block VPNs & Proxies, primarily used for AOF exit traffic, including commercial VPNs, residential proxies, and self-hosted VPNs.

For more details, check out the full article: [Read full article](https://infrawatch.com/blog/the-autonomy-of-the-autonomous-intrusions#blogpost)