---
title: Trivy Compromised Everything You Need to Know about the Latest Supply Chain Attack
date: 2026-03-20
categories: [CYBERSECURITY]
tags: [TRIVY,MALWARE,SUPPLY CHAIN,SECURITY,CYBERATTACK]
---

## Trivy Compromised: Everything You Need to Know about the Latest Supply Chain Attack 🚨

On **March 19, 2026**, threat actors compromised Aqua Security's Trivy vulnerability scanner, injecting credential-stealing malware into official releases and GitHub Actions. Organizations using Trivy should audit their environments immediately. Wiz Research identified a multi-faceted supply chain attack targeting Aqua Security's Trivy, compromising the core scanner, the `trivy-action` GitHub Action, and the `setup-trivy` GitHub Action.

The threat actor, self-identifying as **TeamPCP**, made imposter commits, and at **17:43:37 UTC**, the Trivy repository's `v0.69.4` tag was pushed, triggering a release. This resulted in a malicious checkout that fetched credential stealer code from a typosquatted domain (`scan.aquasecurtiy[.]org`, resolving to `45.148.10.212`), and backdoored binaries being published to GitHub Releases, Docker Hub, GHCR, and ECR.

The attacker also compromised the `aqua-bot` service account, pushing malicious workflows to `tfsec`, `traceeshark`, and `trivy-action` to steal additional credentials, including GPG keys and credentials for Docker Hub, Twitter, and Slack. These secrets were exfiltrated to a Cloudflare Tunnel C2 (`plug-tab-protective-relay.trycloudflare.com`).

### Key Actions to Take 🔍
Security teams should immediately audit Trivy versions: 
- Check whether your organization pulled or executed Trivy `v0.69.4` from any source (GitHub Releases, container registries, etc.) and remove any affected artifacts.
- Audit GitHub Action references: Review workflows using `aquasecurity/trivy-action` or `aquasecuri ty/setup-trivy`. If a version tag rather than a SHA was referenced, check workflow run logs from March 19-20 for signs of compromise.
- Search for exfiltration artifacts, such as repositories named `tpcp-docs` in your GitHub organization.

For more detailed information, read the complete article here: [Read full article](https://www.wiz.io/blog/trivy-compromised-teampcp-supply-chain-attack)