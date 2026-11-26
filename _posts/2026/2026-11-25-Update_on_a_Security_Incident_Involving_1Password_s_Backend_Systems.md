---
title: Update on a Security Incident Involving 1Password's Backend Systems
date: 2026-11-25
categories: [SECURITY]
tags: [1PASSWORD,SECURITY,INCIDENT,CYBERSECURITY]
---

## Update on a Security Incident Involving 1Password's Backend Systems

On **November 19, 2026**, 1Password began investigating indications that an attacker gained access to an employee's corporate GitHub account. The actor used the account to access source code and push malicious code to backend services, which downloaded administrative data pertaining to our customers. This data included customer names and email addresses, in addition to non-secret internal metadata about the account. At no time were customer vault contents accessed by, or available to, the attacker. 🚨

The attacker downloaded account records for a subset of our users. These records include:
- Names and email addresses
- Account and user identifiers, and account creation and last sign-in times
- Public keys (which are public by design, this has no impact on user security)
- Secure Remote Password protocol parameters (which cannot be used to access your account)
- Tokens present in certain emailed links for invitations, provisioning, and account recovery.

During this incident, there were a small number of users in this state, who have been specifically notified. The token is used to complete the invitation or recovery process, but only when combined with an SSO sign-in or a six-digit code sent to the user's registered email address. The token is not able to get access to the account by itself. 

The attacker also copied source code from private repositories and gained access to our CI/CD system. Our source code is not customer data and contains no user secrets. CI/CD contains infrastructure-related secrets in order for our product to work. We have triggered a rotation of all credentials which may have been exposed, and there is no impact on 1Password's services, availability, or product security. 🔒

### What Was Not Affected
- Your vaults and the items in them
- The keys that protect your vaults
- 1Password does not store your account password or secret key
- Account recovery keys
- 1Password apps and browser extensions.

As part of our response, we disabled the affected GitHub account, revoked the stolen token, and removed the access the attacker created. We also rotated or revoked all internal credentials which may have been exposed. Additionally, we lengthened the codes used in invitation and recovery emails from six digits to ten characters as a precautionary measure, making brute force guessing practically impossible. We also tightened internal GitHub, CI/CD, and endpoint controls, and added new detections for this kind of attack. We validated no internal evidence of user account takeovers or compromise using any exposed account provisioning tokens. Independent cybersecurity experts were brought in to validate our containment approaches and remediation efforts. 

For more details, please read the complete article: [Read full article](https://1password.com/blog/update-on-nov-2026-security-incident) 