---
title: Confidential Computing's Core Trust Mechanism is Broken
date: 2026-07-04
categories: [SECURITY]
tags: [CONFIDENTIAL COMPUTING,SECURITY,ATTESTED TLS,VULNERABILITY]
---

## Confidential Computing's Core Trust Mechanism is Broken

🚨 **A Fix May Not Exist!** 🚨

Confidential computing relies on a mechanism called remote attestation, where a server cryptographically proves to a client that it is operating within a genuine, unmodified Trusted Execution Environment (TEE) before any sensitive data is exchanged. Recent research has revealed a significant flaw in the security protocol used for cryptographic trust in this system, known as attested TLS.

### Key Findings

- **Research by Muhammad Usama Sardar** from TU Dresden and his team has formally verified that attested TLS may have a fundamental architectural flaw. Their paper, *Identity Crisis in Confidential Computing*, highlights that diversion attacks can redirect connections intended for one server to a different, compromised machine without the client's knowledge.
- The protocol checks software integrity but not its location, making it vulnerable to exploitation.

### Intra-handshake Attestation

Additionally, the paper *Intra-handshake.fail* explores intra-handshake attestation, where evidence is generated during the TLS handshake. Unfortunately, none of the seven tested methods prevent relay attacks, where a client verifies genuine evidence but ends up encrypting its traffic to a malicious server.

Sardar emphasizes, "In confidential computing, you have to trust the hardware manufacturer anyway... the protocol layer was supposed to provide everything else. His research shows it provides far less than assumed."

### Real-World Implications

This vulnerability is not just theoretical; it affects real-world implementations, including:
- Meta's Private Processing system for WhatsApp
- Edgeless Systems' Contrast
- The open-source Cocos AI platform (versions 0.4.0 to 0.8.2)

The responsible disclosure led to CVE-2026-33697, rated 7.5 (high severity) on the Common Vulnerability Scoring System, significantly higher than BadRAM (5.3).

### Conclusion

As stated by Sardar, "As implemented today, attested TLS is not mature yet... We are investigating further, and we are confident there are more issues yet to be discovered."

For more details, check out the full article here: [Read full article](https://www.theregister.com/security/2026/07/04/confidential-computings-core-trust-mechanism-is-broken-the-fix-may-not-exist/5266056)