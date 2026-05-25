---
title: Megalodon Chums the Waters in 5.5K+ GitHub Repo Poisonings
date: 2026-05-22
categories: [CYBERSECURITY]
tags: [MALWARE,GITHUB,CYBERSECURITY,SUPPLY-CHAIN]
---

## Megalodon Chums the Waters in 5.5K+ GitHub Repo Poisonings 🚨

A malware-spreading scumbag swimming through GitHub pushed malicious commits to more than 5,500 repositories on Monday as part of an automated campaign called **Megalodon**. Similar to the earlier TeamPCP attacks that poisoned about 3,800 GitHub repositories, this new campaign has so far infected **5,561 repos** with CI/CD credential-stealing malware, according to SafeDep researchers, who uncovered the predatory commits and published a full list of the compromised repositories.

If a repository owner merges the commit, the malware executes inside their CI/CD pipeline and propagates further. Ox Security lead researcher **Moshe Siman Tov Bustan** stated, "We've entered a new supply chain attack era, and TeamPCP compromising GitHub was only the beginning. What's coming next is an endless wave, a tsunami of cyber attacks on developers worldwide." He added that hacking GitHub compromises the security of every company with a private repository hosted on the platform.

### What Does Megalodon Do? 🦈
Megalodon steals **AWS secret keys** and **Google Cloud access tokens**. It also queries AWS, Google Cloud Platform, and Azure metadata for instance role credentials, reads SSH private keys, Docker and Kubernetes configurations, Vault tokens, Terraform credentials, and scans source code for more than **30 secret regex patterns**. Then it exfiltrates GitHub tokens, including secrets used to authenticate with cloud providers, thus allowing attackers to impersonate developers' cloud identities, along with Bitbucket tokens. In other words: consider **ALL of your CI/CD variables pwned**.

### The Attack Vector 🔍
SafeDep spotted Megalodon hidden inside a legitimate package: **Tiledesk**, an open-source live chat and chatbot platform. The attacker backdoored versions **2.18.6** (May 19) through **2.18.12** (May 21), and the same npm maintainer published the last clean version, **2.18.5**, before unknowingly publishing these newer compromised versions. The open-source supply-chain security startup researchers said, "The attacker never touched the npm account. They compromised the GitHub repository, and the maintainer published from the poisoned source without realizing it."

While publishing malicious packages on npm is a TeamPCP signature move, Bustan said there's no threat-intel or code-analysis evidence that connects Megalodon to the crew behind the Trivy, Checkmarx, and other recent supply-chain attacks. He told us, "Our best guess now is that it's a different threat actor copying their behavior and style, but not much of the code itself."

### Tracing the Malicious Commit 🔗
SafeDep's threat hunters traced the malicious commit (**acac5a9**) to an author "build-bot," connected to the email address **build-system[@]noreply.dev** with the message "ci: add build optimization step." The author name and noreply email mimic automated CI commits, and there's no GitHub account linked to the author and committer user fields. According to the researchers, "Someone pushed the commit to master with no PR and no merge commit, using a compromised PAT or deploy key."

They searched GitHub for other commits authored by the same email address and found **2,878 results**, plus a second email, **ci-bot@automated.dev**, with an additional **2,841 commits**. All landed May 18 during a six-hour window (11:36 to 17:48 UTC) and targeted **5,561 repositories**. This includes nine compromised Tiledesk repositories: tiledesk-server, tiledesk-dashboard, tiledesk-telegram-connector, tiledesk-llm, tiledesk-docker-proxy, tiledesk-community-app, tiledesk-campaign-dashboard, tiledesk-helpcenter-template, and tiledesk-ai.

For more details, you can read the full article [here](https://www.theregister.com/security/2026/05/22/megalodon-chums-the-waters-in-55k-github-repo-poisonings/5245342).