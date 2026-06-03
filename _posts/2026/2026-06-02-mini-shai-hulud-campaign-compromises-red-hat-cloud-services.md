---
title: Mini Shai-Hulud Campaign Compromises Red Hat Cloud Services
date: 2026-06-02
categories: [CYBERSECURITY]
tags: [MALWARE,RED-HAT,NPM,SECURITY]
---

## Mini Shai-Hulud Campaign Compromises Red Hat Cloud Services 🚨

A mini Shai-Hulud campaign has compromised Red Hat Cloud Services npm packages to steal developer and CI/CD secrets during installation. Socket has detected a malicious npm supply chain campaign involving compromised `@redhat-cloud-services` packages published under the Red Hat Cloud Services namespace. This campaign employs tactics such as install-time execution, credential harvesting, CI/CD targeting, encrypted exfiltration, and potential downstream propagation. Attribution remains unclear, as publicly available tools lower the barrier to entry for a broad range of threat actors to conduct similar operations.

### Key Findings 🔍

- The affected package versions execute an obfuscated payload through a `preinstall` hook, allowing the malware to run automatically during `npm install` before a developer imports or uses the package.
- The payload is designed to collect sensitive information including GitHub Actions secrets, npm tokens, cloud credentials, Kubernetes and Vault material, SSH keys, and Git credentials.
- Encrypted exfiltration logic and GitHub-based fallback mechanisms indicate that the attacker aimed not only to steal credentials but also to enable further supply chain propagation.

### Technical Details ⚙️

Socket AI Scanner's analysis of `@redhat-cloud-services/chrome@2.3.1` highlights the package's install/import-time JavaScript loader, which reconstructs hidden source through runtime decoding and decrypts embedded payload blobs with AES-128-GCM. This behavior confirms that the malicious functionality is intentionally concealed from static review and staged for second-stage credential theft, environment inspection, and outbound communication.

Affected packages utilize multiple obfuscation and staging layers. The `package.json` contains: 
```json
"scripts": { "preinstall":"node index.js" }
```
This causes the malicious loader to execute automatically before installation completes. The packages may appear to offer normal Red Hat Cloud Services functionality, but their CommonJS entry point is the malicious loader.

### Conclusion 🛡️

The `index.js` file begins with a char-code array, Caesar/ROT-style transform, and `eval`, which decodes into an async wrapper that imports Node crypto APIs and decrypts embedded payloads. This sophisticated approach highlights the need for vigilance in npm package management.

For further details, read the complete article here: [Read full article](https://socket.dev/blog/mini-shai-hulud-campaign-hits-red-hat-cloud-services-npm-packages)