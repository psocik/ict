---
title: Google Quantum-Proofs HTTPS by Squeezing 15kB of Data into 700-Byte Space
date: 2026-02-28
categories: [TECHNOLOGY]
tags: [GOOGLE,QUANTUM,HTTPS,SECURITY,ENCRYPTION]
---

## Google Quantum-Proofs HTTPS 🚀

Google on Friday unveiled its plan for its Chrome browser to secure HTTPS certificates against quantum computer attacks without breaking the Internet. The quantum-resistant cryptographic data needed to transparently publish TLS certificates is roughly 40 times bigger than the classical cryptographic material used today. A typical X.509 certificate chain used today comprises six elliptic curve signatures and two EC public keys, each of them only 64 bytes. The full chain is roughly 4 kilobytes.

Bas Westerbaan, principal research engineer at Cloudflare, which is partnering with Google on the transition, said that the massive size increase can also degrade “middle boxes,” which sit between browsers and the final site.

To bypass the bottleneck, companies are turning to **Merkle Trees**, a data structure that uses cryptographic hashes and other math to verify the contents of large amounts of information using a small fraction of material used in more traditional verification processes in public key infrastructure. Merkle Tree Certificates replace the heavy, serialized chain of signatures found in traditional PKI with compact Merkle Tree proofs. In this model, a Certification Authority (CA) signs a single ‘Tree Head’ representing potentially millions of certificates, and the ‘certificate’ sent to the browser is merely a lightweight proof of inclusion in that tree. The MTCs use Merkle Trees to provide quantum-resistant assurances that a certificate has been published without having to add most of the lengthy keys and hashes.

Once viable, Shor’s algorithm could be used to forge classical encryption signatures and break classical encryption public keys of the certificate logs. To rule out this possibility, Google is adding cryptographic material from quantum-resistant algorithms such as ML-DSA. This addition would allow forgeries only if an attacker were to break both classical and post-quantum encryption. The new regime is part of what Google is calling the quantum-resistant root store, which will complement the Chrome Root Store the company formed in 2022.

Using other techniques to reduce the data sizes, the MTCs will be roughly the same 4kB length they are now, Westerbaan said.

The new system has already been implemented in Chrome. For the time being, Cloudflare is enrolling roughly 1,000 TLS certificates to test how well the MTCs work. The Internet Engineering Task Force standards body has recently formed a working group called the PKI, Logs, And Tree Signatures, which is coordinating with other key players to develop a long-term solution. 

> “We view the adoption of MTCs and a quantum-resistant root store as a critical opportunity to ensure the robustness of the foundation of today’s ecosystem,” Google’s Friday blog post said. “By designing for the specific demands of a modern, agile internet, we can accelerate the adoption of post-quantum resilience for all web users.”

[Read full article](https://arstechnica.com/security/2026/02/google-is-using-clever-math-to-quantum-proof-https-certificates/)