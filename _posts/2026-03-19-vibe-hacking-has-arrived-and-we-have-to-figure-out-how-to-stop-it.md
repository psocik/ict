---
title: Vibe Hacking Has Arrived - And We Have to Figure Out How to Stop It
date: 2026-03-19
categories: [CYBERSECURITY]
tags: [VIBE HACKING,CYBERSECURITY,AI,OFFENSIVE CYBER,DATA BREACH]
---

## Vibe Hacking Has Arrived 🚀

The same dynamic has played out in offensive cyber, and a recent breach in Mexico is the clearest proof yet. According to researchers at Gambit Security, an unknown actor used Anthropic's Claude Code in a month-long campaign beginning in late December 2025, targeting Mexico's federal tax authority, the national electoral institute, Mexico City's civil registry, multiple state governments, and Monterrey's water utility. More than 1,000 prompts later, the attacker exfiltrated 150 gigabytes of government data, including records tied to 195 million taxpayers.

Around the third week, the operator couldn't figure out lateral movement. So they opened a ChatGPT session and asked for help: how to move through the compromised networks, which credentials were needed for which systems, and how likely the operation was to get detected. This was someone who needed a second chatbot to explain what to do when the first chatbot's plan stopped working. A year ago, this person probably couldn't have breached a single Mexican government agency.

What generative video did to VFX is what LLMs will do to offensive tradecraft. The Mexico campaign isn't the most sophisticated attack ever run, but it looks like it was run by someone who knows what they're doing. In both cases, the model supplied the competence the human lacked. The Mexico case represents one example in a growing body of evidence.

In February, AWS published findings on a low-to-medium skill actor, likely a single person, who used commercial AI to compromise more than 600 FortiGate devices across 55 countries in five weeks. No zero-days involved, just exposed management ports and weak credentials, scaled by AI-generated tooling. Additionally, Anthropic has disclosed a case involving a solo operator who automated recon, credential harvesting, and ransom note generation across 17 organizations in a single month. These are script kiddies suddenly able to punch well above their weight class.

Google's Threat Intelligence Group (GTIG) noted in late 2025 that while LLMs have become essential to state-backed actors' research and targeting, they haven't observed anyone developing genuinely new capabilities that alter the threat landscape. In other words, AI hasn't raised the ceiling much, but it's raising the floor significantly. AI gave them the speed to churn through hundreds of poorly defended environments at a pace that used to require a team. A mediocre operator who can credibly hit hundreds of soft targets simultaneously represents a different kind of problem than a sophisticated attacker going after one hard target.

Today, we're looking at a multi-model workflow, which matters for anyone who thinks guardrails alone solve the problem. The Mexico attacker bounced between Claude and ChatGPT. While it's important to make individual models refuse malicious prompts, it's not going to contain this threat on its own. Google documented malware that queries LLMs mid-execution to generate recon commands on the fly: not a human copying an answer, but code calling a model API as part of its own execution loop. The skill floor in offensive cyber has risen sharply, and it will keep rising every quarter the models improve. The models aren't just helping experts move faster. They're handing attack capability to people who never had the skills to run one.

[Read full article](https://www.scmagazine.com/perspective/vibe-hacking-has-arrived-and-we-have-to-figure-out-how-to-stop-it)