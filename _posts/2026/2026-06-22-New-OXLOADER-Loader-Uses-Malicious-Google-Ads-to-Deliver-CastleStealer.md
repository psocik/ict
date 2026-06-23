---
title: New OXLOADER Loader Uses Malicious Google Ads to Deliver CastleStealer
date: 2026-06-22
categories: [CYBERSECURITY]
tags: [MALWARE,GOOGLE-ADS,CYBERSECURITY,CASTLESTEALER]
---

## New OXLOADER Loader Uses Malicious Google Ads to Deliver CastleStealer 🚨

Cybersecurity researchers have disclosed details of a new campaign that delivers **CastleStealer** through a previously unreported malware loader called **OXLOADER**. According to Elastic Security Labs, this campaign leverages malicious Google Ads as a starting point to distribute the malware.

Evidence indicates that the threat actor is likely Russian-speaking and financially motivated, as they have implemented explicit exclusions to prevent infecting machines located in the Commonwealth of Independent States (CIS) region. The campaign has been codenamed **REF8372**.

### How the Attack Works 🔍
The attack begins when unsuspecting users enter queries such as "lts version of node.js" on search engines like Google, redirecting them to a fake website ("node-js[.]prentiva99[.]info") surfaced via bogus ads published under the verified name **ВОЛОДИМИР ТЕРЕЩЕНКО**, purportedly based in Ukraine. The advertiser account, along with its ad campaigns, was removed from Google on **May 14, 2026**.

Users who interact with the site are served a batch script hosted on **Storj**, a decentralized, open-source cloud storage platform. This abuse of Storj illustrates how threat actors continue to leverage legitimate services to evade domain-based reputation filters. Running the batch script displays a bogus installation wizard user interface (UI), while stealthily downloading a next-stage payload, a Storj-hosted executable dubbed **OXLOADER** through a PowerShell command and executing it with `-Verb RunAs` to trigger a Windows User Account Control (UAC) prompt.

### Technical Breakdown 🛠️
The attack employs DLL side-loading to launch a rogue DLL, which then proceeds to decrypt and execute the CastleStealer payload. Researchers Daniel Stepanic and Jia Yu Chan noted that "The loader uses several obfuscation layers (control-flow flattening, opaque predicates, mixed Boolean-Arithmetic), self-modifying decryption stubs, and abuses the Windows .reloc section to stage shellcode." OXLOADER also utilizes techniques like control-flow flattening (CFF) and mixed Boolean-Arithmetic (MBA) to evade static detection, while ensuring it is not run in sandboxed environments.

Elastic noted that "OXLOADER is in an early operational phase, but the engineering behind it suggests this family is worth watching." The researchers further stated that "The code obfuscation, anti-VM measures, benign-looking code used to masquerade its binaries, and unique staging techniques reflect deliberate engineering choices to evade analysis." This investment, according to Elastic, "is paying off, resulting in low detection rates across static engines and detonation runs, giving OXLOADER a window to operate before it gets hunted down." 

For more details, check out the full article here: [Read full article](https://thehackernews.com/2026/06/new-oxloader-loader-uses-malicious.html)