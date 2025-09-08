---
title: GhostAction Supply Chain Attack Compromises 3000+ Secrets
date: 2025-09-08
categories: [SECURITY]
tags: [GHOSTACTION,SUPPLY CHAIN ATTACK,GITHUB,SECRETS,CYBERSECURITY]
---

Hundreds of GitHub users and repositories have been hit by another supply chain attack, in which threat actors have already stolen more than 3000 secrets, according to GitGuardian. The security vendor first noticed suspicious activity related to a GitHub repository associated with the FastUUID project, on September 5. A compromised maintainer had pushed a malicious commit three days earlier. This contained a GitHub action workflow file designed to steal secrets, specifically a PyPI token.

“While this token should have allowed the actor to compromise the FastUUID package on PyPI, we found no evidence of malicious package releases during the compromise window,” GitGuardian explained. “The attacker's inaction during the three days following the initial compromise suggested FastUUID was not the primary target. Our investigation revealed a much larger operation.\n\n[Read the full article here](https://www.infosecurity-magazine.com/news/ghostaction-supply-chain-3000/) 
