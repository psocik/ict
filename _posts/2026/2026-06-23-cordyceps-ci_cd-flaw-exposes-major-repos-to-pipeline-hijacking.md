---
title: Cordyceps CI/CD Flaw Exposes Major Repos to Pipeline Hijacking
date: 2026-06-23
categories: [CYBERSECURITY]
tags: [CYBERSECURITY,VULNERABILITY,PIPELINE,REPOS]
---

## Major Vulnerability Discovered in CI/CD Systems 🚨

A significant software supply chain vulnerability has been identified across the open-source network, allowing cybercriminals to hijack build pipelines and compromise corporate networks. Cybersecurity research firm Novee uncovered this structural flaw, named **Cordyceps** after a body-snatching parasitic fungus. This vulnerability is a systemic class of Continuous Integration and Continuous Deployment (CI/CD) flaws, existing within GitHub Actions workflows (specifically in .yml configuration files).

### How It Works 🔍

Researchers found that an unauthenticated user doesn't need special organization privileges to launch an attack; a free, anonymous online account suffices to forge approvals, inject malicious code, or steal permanent credentials. Standard automated scanners often miss this risk as they only examine single files in isolation. In contrast, Cordyceps relies on multi-step exploit chains where untrusted data tricks the system by crossing a security boundary.

In a hypothetical command injection and artifact poisoning attack, an unauthorized user could leave an anonymous comment or submit a malicious code update, known as a pull request. A low-privilege workflow treats this input as a trusted command, executing hidden code that compromises the final software package or artifact. This process could allow an external threat actor to gain full administrative permissions over a company's cloud network.

### Impact on Major Companies 🌐

Novee scanned approximately 30,000 high-impact open-source repositories, flagging 654 projects in a single scan, with over 300 confirmed fully exploitable. The security team verified flaws across major infrastructure systems, affecting companies like Microsoft, Google, Apache, Cloudflare, and the Python Software Foundation. For instance, in Microsoft Azure Sentinel, researchers demonstrated that an anonymous comment on a pull request could enable an attacker to execute code and steal a non-expiring GitHub App key, granting write access to security content deployed directly to customer workspaces via the Azure Marketplace.

Similarly, researchers targeted Google's AI Agent Development Kit sample repository (adk-samples), where a single malicious pull request was shown to grant full ownership roles over the associated Google Cloud project.

### Rising Threats ⚠️

Further investigation revealed that attackers could also run unauthorized commands on Cloudflare's Workers SDK toolchain, steal saved login credentials from the Apache Doris database, and snatch automation tokens from Black, a popular Python code tool handling 130 million downloads monthly. All tested vulnerabilities have since been reported and fixed. Researchers noted that such flaws are rapidly increasing as AI coding agents generate configuration files at an exponential pace, persistently reproducing insecure structural patterns across millions of untested repositories.

Since anonymous users can exploit these flawed pipelines to manipulate major corporate platforms without authorization, researchers described the risk as "puppeteering the repositories of some of the world's biggest companies, silently manipulating their workflows." 

For more details, check out the full article: [Read full article](https://hackread.com/cordyceps-ci-cd-flaw-microsoft-google-apache-repos-hijack/)