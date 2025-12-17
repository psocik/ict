---
title: China's Ink Dragon Hides Out in European Government Networks
date: 2025-12-16
categories: [APT]
tags: [CHINA,ESPIONAGE,CYBERSECURITY]
---

Chinese espionage crew Ink Dragon has expanded its snooping activities into European government networks, using compromised servers to create illicit relay nodes for future operations. The campaign has hit "several dozen victims," Check Point Software group manager Eli Smadja told The Register. This includes government entities and telecommunications organizations across Europe, Asia, and Africa. 

"While we cannot disclose the identities or specific countries of affected entities, we observed the actor beginning relay-based operations in the second half of 2025, followed by a gradual expansion in victim coverage from each relay over time," Smadja said. These attacks begin with Ink Dragon probing security weaknesses, such as misconfigured Microsoft IIS and SharePoint servers, to gain access to victims' environments. This tactic, as opposed to abusing zero-days or other high-profile vulnerabilities, helps attackers fly under the radar and reduces their chances of being caught.

Ink Dragon then scoops up credentials and uses existing accounts to infiltrate targets, tactics that help the gang blend in with normal network traffic. "This stage is typically characterized by low noise and spreads through infrastructure that shares the same credentials or management patterns," Check Point's researchers said in a Tuesday blog. Once Ink Dragon finds an account with domain-level access, the spies set to work establishing long-term access across high-value systems, installing backdoors and implants that store credentials and other sensitive data.

Additionally, Check Point says the cyber spies have updated their FinalDraft backdoor so that it blends in with common Microsoft cloud activity, hiding its command traffic inside mailbox drafts. The new version also lets the malware check in during business hours - so as not to draw unwanted after-hour attention - and can more efficiently transfer large files with minimal noise. Once it's established long-term access on compromised servers, the attack group co-opts victims' infrastructure, deploying customized IIS-based modules on public-facing servers to create relay points for their illicit movement.

"These servers forward commands and data between different victims, creating a communication mesh that hides the true origin of the attack traffic," Check Point Research said.

The threat hunters' investigation into Ink Dragon also uncovered similar, stealth activity by another China-linked espionage crew RudePanda, which "had quietly entered several of the same government networks," they wrote. While the two groups are unrelated, they both abused the same server vulnerability to gain access to the same IT environments. 

This also illustrates the changing tactics among other government-sponsored cyber squads, including not only Beijing-backed crews, but also those from Russia. According to a Monday security alert, Amazon sounded the alarm on similar relay-node activity, ongoing since at least 2021. The cloud giant attributed this campaign to Russia's Main Intelligence Directorate (GRU), and said it primarily targeted Western countries' energy, telecommunications, and tech providers, stealing credentials and compromising misconfigured devices hosted on AWS to give the Kremlin's snoops persistent access to sensitive networks.

[Read the complete article](https://www.theregister.com/2025/12/16/chinas_ink_dragon_hides_out/) 