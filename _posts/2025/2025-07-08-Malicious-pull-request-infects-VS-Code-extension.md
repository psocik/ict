---
title: Malicious pull request infects VS Code extension
date: 2025-07-08
categories: [SECURITY]
tags: [MALICIOUS SOFTWARE,VC CODE,CRYPTOCURRENCY,SUPPLY CHAIN ATTACKS]
---

In the last few months, Reversing Labs (RL) researchers have encountered multiple malicious packages that target cryptocurrency users and developers. In May, RL researcher Karlo Zanki wrote a blog about malicious PyPI packages that target developers in the Solana ecosystem. Another RL researcher, Lucija Valentić, wrote about malicious npm packages that steal crypto funds from wallets by injecting code into local, legitimate packages. Those are notable incidents.

Every day the RL research team detects packages like simple infostealers, backdoors, or downloaders that have been published to open source repositories. Most of the time these packages mimic legitimate open source packages with similar names (attacks known as "typosquatting"). Or they publish new modules that reproduce code and functionality from existing, legitimate packages but add subtle, malicious features that are easily overlooked by rushed developers. In each case, attackers are counting on unsuspecting developers downloading their malicious packages in order to run their payload.

But mimicking legitimate packages isn’t the only form of software supply chain attack. The hacks of SolarWinds Orion, 3CX’s DesktopApp, and the malicious compromise of the widely used open source compression tool XZ Utils, are examples of more sophisticated supply chain compromises that involve development pipelines of trusted commercial and open-source projects and result in unsanctioned code tampering or the insertion of malicious code into trusted code bases.

This type of supply chain attack is less common, but it is more effective than simple typosquatting attacks. If successful, these attacks can impact hundreds or thousands of end-user organizations with serious consequences.

[Read the complete article here](https://www.reversinglabs.com/blog/malicious-pull-request-infects-vscode-extension).