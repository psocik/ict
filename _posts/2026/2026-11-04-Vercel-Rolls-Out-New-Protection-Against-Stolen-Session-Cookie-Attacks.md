---
title: Vercel Rolls Out New Protection Against Stolen Session Cookie Attacks
date: 2026-11-04
categories: [SECURITY]
tags: [VERCEL,SECURITY,COOKIES,MALWARE,TECHNOLOGY]
---

## Vercel Rolls Out New Protection Against Stolen Session Cookie Attacks 🚀

Vercel is gradually rolling out **Device Bound Session Credentials (DBSC)** on its platform as a key defense against information stealer malware. This new feature, announced by Vercel's CTO Malte Ubl on X, binds a login session to the user's device with a private key stored in a TPM, ensuring that even if the session cookie is stolen, it cannot be reused on another device.

The announcement specifically concerns logins to Vercel's platform at [vercel.com](https://vercel.com), where developers manage their projects and deployments. Ubl explained that "DBSC works by storing a private key in your device's TPM (the same device that the fingerprint sensor or similar biometric devices on your laptop or phone uses) and using that key to sign your cookie." He further stated, "The private key can never be retrieved ever again. Not by us, not by you, not by the malware."

Vercel's DBSC rollout also complements Chrome's **App-Bound Encryption**, which already makes it harder for infostealer malware to extract browser cookies. DBSC adds another critical layer of protection by preventing stolen session cookies from being reused on other devices. Currently, DBSC functions in Chrome on macOS and Windows, with the rollout being gradual to appropriately handle edge cases involving OAuth apps. 

Separately, Vercel is implementing a similar protective technology called **DPoP** for the Vercel CLI.

Additionally, Vercel launched **Security Review** in public beta for Pro and Enterprise teams earlier this week. This new feature for the Vercel Agent scans code changes on every push to connected GitHub repositories once enabled. The system uses code and team-defined policies to flag issues such as missing authorization checks and exposed secrets. If permissions allow, the Vercel Agent can validate and commit fixes. Vercel stated that Security Review scans will be free until **November 10, 2026**, while agent-generated fixes will be billed separately. Ubl noted that Vercel's security team had deployed this feature internally months prior, where it "already proven its worth," leading to its broad availability.

These security enhancements follow a breach Vercel experienced in April, impacting a subset of customers. Attackers gained access to Vercel's systems by compromising an employee's Google Workspace account at Context.ai. Vercel reported that the attacker utilized this access to reach internal systems and view environment variables that had not been marked as sensitive. A threat actor impersonating ShinyHunters subsequently attempted to sell allegedly stolen source code, access keys, and database data.

To read the complete article see: [Read full article](https://www.bleepingcomputer.com/news/security/vercel-rolls-out-new-protection-against-stolen-session-cookie-attacks/) 
