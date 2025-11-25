---
title: FAQ About Sha1-Hulud 2.0  The "Second Coming" of the npm Supply-Chain Campaign
date: 2025-11-24
categories: [SECURITY]
tags: [MALWARE,NPM,SUPPLY-CHAIN,SHA1-HULUD]
---

A massive resurgence of the Sha1-Hulud malware family, dubbed "The Second Coming" by its creators, has been observed targeting the npm ecosystem, beginning around November 24. The attackers compromised at least 800 high-profile publisher accounts to upload trojanized versions of legitimate packages. Cloud security teams are advised to immediately audit their environments for at least 800 compromised packages.

Unlike previous iterations, these malicious packages contain new payloads and execute using install lifecycle scripts to compromise developer environments and CI/CD pipelines at scale. The attack chain begins when a developer installs a compromised package containing a modified manifest file. A preinstall lifecycle script is injected into the package.json, immediately triggering a file named setup_bun.js upon installation. The malware then downloads and installs the Bun runtime, a separate JavaScript environment, and uses it to execute a bundled payload, often named bun_environment.js. This "bring your own runtime" technique allows the malicious code to operate outside the visibility of standard Node.js security tools.

The impact of this campaign is extensive, reportedly affecting tens of thousands of GitHub repositories, including high-profile integrations from Zapier, ENS Domains, and Postman. By hijacking trusted publisher accounts, the attackers successfully poisoned the supply chain at a fundamental level, forcing malicious code into numerous corporate environments through routine dependency updates. The malware is also significantly more aggressive than in previous campaigns, with attempts to destroy the victim’s home directory and, in some cases, delete all writable files owned by the user.

Cloud security teams should immediately audit their environment using a security scanner to check for malicious versions of the affected packages and remove them by upgrading to a later version. Tenable products can be used to automatically and proactively detect malicious packages associated with the Sha1-Hulud campaigns across both on-premises and cloud environments. Plugin ID 265897 can be used to identify compromised packages affected in the Sha1-Hulud campaigns. Tenable Cloud Security classifies affected packages as malicious and will display detected packages in the Tenable Console environment.

To read the complete article see:
[FAQ About Sha1-Hulud 2.0 : The "Second Coming" of the npm Supply-Chain Campaign](https://www.tenable.com/blog/faq-about-sha1-hulud-2-0-the-second-coming-of-the-npm-supply-chain-campaign)