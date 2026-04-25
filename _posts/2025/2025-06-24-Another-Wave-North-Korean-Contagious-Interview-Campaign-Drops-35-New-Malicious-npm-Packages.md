---
title: Another Wave North Korean Contagious Interview Campaign Drops 35 New Malicious npm Packages
date: 2025-06-24
categories: [RESEARCH]
tags: [NORTH KOREA,MALICIOUS PACKAGES,SECURITY,NPM]
---

The Socket Threat Research Team has uncovered an extended and ongoing North Korean supply chain attack that hides behind typosquatted npm packages. Threat actors linked to the Contagious Interview operation published 35 malicious packages across 24 npm accounts. Six remain live on the registry (react-plaid-sdk, sumsub-node-websdk, vite-plugin-next-refresh, vite-loader-svg, node-orm-mongoose, and router-parse), and together have been downloaded over 4,000 times. We have petitioned the npm security team to remove the remaining live packages and suspend the associated accounts.

Each malicious package contains a hex-encoded loader we call HexEval. When the package is installed, HexEval Loader collects host metadata, decodes its follow-on script, and, when triggered, fetches and runs BeaverTail, the infostealing second-stage malware linked to the Democratic People’s Republic of Korea (DPRK) attackers. BeaverTail, in turn, references a third-stage backdoor InvisibleFerret, giving the threat actors layered control over the victim’s machine. This nesting-doll structure helps the campaign evade basic static scanners and manual reviews. One npm alias also shipped a cross-platform keylogger package that captures every keystroke, showing the threat actors’ readiness to tailor payloads for deeper surveillance when the target warrants it.

Posing as recruiters on LinkedIn, the North Korean threat actors send coding “assignments” to developers and job seekers via Google Docs, embed these malicious packages within the project, and often pressure candidates to run the code outside containerized environments while screen-sharing.

**Read the complete article here:** [North Korean Contagious Interview Campaign Drops 35 New Malicious npm Packages](https://socket.dev/blog/north-korean-contagious-interview-campaign-drops-35-new-malicious-npm-packages) 

💼 *Working at Team Cymru is more than a job — it’s a chance to be part of something meaningful. Enjoy outstanding benefits, work with incredible people, and contribute to a mission that truly matters.*

👉 [Explore open roles and join us here!](https://www.team-cymru.com/careers) 

---