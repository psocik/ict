---
title: Stop Evaluating What to Patch by CVSS Score Alone
date: 2026-10-16
categories: [SECURITY]
tags: [AI,VULNERABILITIES,SECURITY,CVSS,ATTACK-PATHS]
---

## Stop Evaluating What to Patch by CVSS Score Alone

**Published on:** October 16, 2026  
**Source:** SC Magazine

Security teams have spent years prioritizing vulnerabilities based on CVSS severity or the potential of attackers to exploit them in isolation. However, they have struggled to understand the complete picture of how attackers can combine multiple weaknesses across assets to reach critical targets. 🤖💥  

AI agents change that calculation because they can spend hours exploring paths that a human attacker would abandon after a few minutes. They can test multiple routes simultaneously, recover from failed attempts, and work through a chain of seemingly insignificant weaknesses until they reach something valuable. Security teams now have to contend with a growing number of attack paths that their existing prioritization methods may overlook.

In August 2026 alone, the average enterprise accumulated dozens of new attack paths to its most sensitive systems. Only 25% of these paths were within the practical capabilities of human attackers. The remaining 75% exceeded those limits but were still viable for autonomous AI agents. The rate at which these machine-viable paths appeared has quadrupled year over year, compared with a more modest increase for human-viable paths. The number of these paths exploitable by AI has grown in part because of advancements in AI models, first seen in Mythos and now in open weight models like GLM 5.3. The paths themselves also run considerably deeper. The median machine-viable path crossed eight assets and five trust boundaries, compared with four assets and two trust boundaries for human-viable paths. An autonomous agent can continue testing the chain while other agents investigate alternatives, making vulnerabilities that once seemed too difficult to exploit considerably more attractive. 🔍🔐

Most enterprise security programs still rely heavily on CVSS severity scores to determine what gets fixed first. The trouble comes when teams evaluate findings individually without considering how an attacker could connect them. Our research found that 7% of critical attack paths consisted entirely of low- and medium-severity vulnerabilities. Each weakness might fall below an organization's remediation threshold, yet an attacker who successfully chains them together could reach a critical asset. These paths also tend to remain available for a long time. Eighty-three percent of machine-viable paths persisted for more than 30 days, compared with half of human-viable paths. Organizations can spend weeks addressing high-severity vulnerabilities while leaving intact a route to sensitive systems built entirely from findings that their security programs consider relatively unimportant.

Security teams need to understand how risks connect across their environments, which requires bringing together information from vulnerability scanners, endpoint tools, identity platforms, and cloud security products. In our research, reconstructing the median critical attack path required correlating information from five different security tools. Organizations should prioritize identifying which changes eliminate the greatest amount of exploitable risk. As autonomous agents make longer and more complicated attacks practical, security teams need to reconsider how they decide which vulnerabilities deserve attention. 🔒💡

[Read full article](https://www.scmagazine.com/perspective/stop-evaluating-what-to-patch-by-cvss-score-alone)