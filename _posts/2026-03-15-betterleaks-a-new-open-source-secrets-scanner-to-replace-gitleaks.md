---
title: Betterleaks A New Open-Source Secrets Scanner to Replace Gitleaks
date: 2026-03-15
categories: [SECURITY]
tags: [BETTERLEAKS,GITLEAKS,OPENSOURCE,SECRETSCANNER]
---

## Introducing Betterleaks 🚀

A new open-source tool called **Betterleaks** has been launched to scan directories, files, and git repositories to identify valid secrets using default or customized rules. Secret scanners are specialized utilities that help developers find sensitive information, such as credentials, API keys, private keys, and tokens, that may have been accidentally committed in source code. 

Since threat actors often scan configuration files in public repositories for sensitive details, tools like Betterleaks are essential for identifying secrets and protecting them before attackers can exploit them. Betterleaks is designed as a more advanced successor to Gitleaks and is maintained by the same team, with support from Aikido. 

### Key Features 🔑
- **Rule-defined validation** using CEL (Common Expression Language).
- **Token Efficiency Scanning** based on BPE tokenization, achieving **98.6% recall** compared to **70.4%** with entropy on the CredData dataset.
- A **Pure Go implementation** with no CGO or Hyperscan dependency.
- Automatic handling of doubly/triply encoded secrets.
- An expanded rule set for more providers.
- **Parallelized Git scanning** for faster repository analysis.

The developer has also revealed exciting features planned for the next version of Betterleaks, including support for additional data sources beyond Git repositories and files, LLM-assisted analysis for better secret classification, more detection filters, automatic secret revocation via provider APIs, permissions mapping, and performance optimizations. 

### Governance and Philosophy 🏛️
Betterleaks operates under the open-source MIT license and is maintained by three additional contributors, including members from the Royal Bank of Canada, Red Hat, and Amazon. The design philosophy of Betterleaks combines human-centric use with accommodation for AI agent workflows, including CLI features optimized for automated tools that scan AI-generated code.

To read the complete article see:
[Read full article](https://www.bleepingcomputer.com/news/security/betterleaks-a-new-open-source-secrets-scanner-to-replace-gitleaks/)