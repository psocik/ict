---
title: npm Adds 2FA-Gated Publishing and Package Install Controls Against Supply Chain Attacks
date: 2026-05-23
categories: [SECURITY]
tags: [NPM,2FA,SUPPLY CHAIN,SECURITY,GITHUB]
---

## npm Enhances Security with 2FA-Gated Publishing 🚀

GitHub has rolled out new controls for npm to improve the security of the software supply chain, giving maintainers the ability to explicitly approve a release prior to the packages becoming publicly available for installation. 

Called **staged publishing**, this feature is now generally available on npm. It mandates that a human maintainer pass a **two-factor authentication (2FA)** challenge to approve a package before it is pushed to npmjs.com. 

> "Instead of a direct publish that immediately makes a package version available to consumers, the prebuilt tarball is uploaded to a stage queue where a maintainer must explicitly approve it before it becomes installable," GitHub said. This change ensures **proof of presence** for every publish, including those that come from non-interactive CI/CD workflows and trusted publishing with OpenID Connect (OIDC) authentication.

### Requirements for Staged Publishing
Before using staged publishing, package maintainers must meet the following criteria:
- Have publish access to the package
- The package already exists on the npm registry (a brand new package cannot be staged)
- 2FA is enabled for the account

Developers can use the command `npm stage publish` from the root directory of the package to submit it to a staging area. To use this command, it's essential to update to npm CLI **11.15.0** or newer. For optimal protection, GitHub recommends pairing staged publishing with trusted publishing using OIDC.

### New Install Source Flags
Additionally, a second update focused on npm relates to the introduction of three new install source flags alongside the existing `--allow-git` flag. These flags include:
- `--allow-file`: controls installs from local file paths and local tarballs
- `--allow-remote`: controls installs from remote URLs, including https tarballs
- `--allow-directory`: controls installs from local directories

These flags allow developers to apply the same explicit-allowlist approach to every non-registry install source.

This development comes amid a massive surge in software supply chain attacks targeting open-source ecosystems over the past few months, with one cybercriminal group known as **TeamPCP** engaging in poisoning popular packages at an unprecedented scale through a self-perpetuating cycle of compromises.

[Read full article](https://thehackernews.com/2026/05/npm-adds-2fa-gated-publishing-and.html)