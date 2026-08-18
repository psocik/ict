---
title: Massive ChainDrop npm Supply-Chain Attack Infects Hundreds of Packages
date: 2026-08-04
categories: [SECURITY]
tags: [NPM,MALWARE,SUPPLY-CHAIN,SECURITY]
---

## Massive ChainDrop npm Supply-Chain Attack Infects Hundreds of Packages 🚨

Self-propagating malware named **ChainDrop** has compromised more than **1,300 packages** with a combined **2 billion monthly downloads** on the Node Package Manager (npm) registry. Infected packages include very popular ones such as **Keyv** and **Cacheable**, flat-cache, and file-entry-cache, all caching utilities from the same maintainer.

The supply-chain attack started after the threat actor compromised the GitHub account of Keyv's maintainer, and quickly spread to packages associated with major organizations such as **Deliveroo**, **Ornikar**, **OneReach**, **Picsart**, **Qlik**, and **ServiceTitan**. Multiple application security companies spotted the attack and discovered that it deployed a **Shai-Hulud-based worm** named ChainDrop. A report from Aikido states that **at least 868 packages** (across 1381 versions) have been compromised by the worm.

The poisoned packages contain two files: the **setup.mjs** payload dropper and the **Math_Symbol.js** script for stealing sensitive information, as well as a `"preinstall": "node setup.mjs"` entry in their package.json configuration file. **Aikido researchers warn** that anyone who ran `npm install` against an affected version would have had **setup.mjs** execute automatically before their install completed.

The **setup.mjs** dropper downloads the **Bun JavaScript runtime** from the official GitHub release to execute **Math_Symbol.js**, the malicious payload with infostealing capabilities. After downloading the Bun executable to run the infostealer script, **setup.mjs** deletes the temporary runtime directory. Aikido notes that the infostealer collects developer and cloud credentials from the compromised environment and encrypts them before sending them to a public GitHub repository with the description **"Shai-Hulud: Here We Go Again."**

The malware searches infected development systems and CI/CD runners for credentials that could grant it access to additional source code repositories and npm packages, and collects the following types of data:
- The complete process environment.
- Local configuration and credential files.
- GitHub PATs, workflow tokens, and other ghp_, gho_, and ghs_ tokens.
- npm tokens beginning with npm_.
- GitHub Actions secrets, including code designed to extract `"isSecret":true` values from a self-hosted runner.
- AWS credentials, SSM Parameter Store values using **WithDecryption: true**, and Secrets Manager secrets.
- Kubernetes secrets from accessible namespaces.
- HashiCorp Vault tokens and KV secrets.
- Database credentials, private keys, Stripe, Slack, Twilio, Azure, and GCP credentials.

According to cloud security company **Wiz**, the **npm-cache[.]com** domain is also being used for exfiltrating data and should be treated as a strong indicator of compromise.

If an affected package version was installed, system administrators should treat the developer workstation or CI/CD runner as compromised even if the package was subsequently removed. In such instances, it is recommended to rebuild systems from safe backups or from scratch, rotate all tokens that were accessible from the impacted environment, and review logs for unauthorized access and repositories for unexpected commits or changes.

As the attack is still unfolding, the number of packages and exact malicious versions is expected to grow, so it is important to continue using **dependency allowlisting**, **integrity checks**, and **provenance controls**. A list of compromised npm packages is available from Wiz, StepSecurity, Aikido, Socket, and Ox Security. The security companies also provide a list of indicators of compromise that include hashes for malicious files and artifacts, and network data.

[Read full article](https://www.bleepingcomputer.com/news/security/massive-chaindrop-npm-supply-chain-attack-infects-hundreds-of-packages/)