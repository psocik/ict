---
title: Cloudflare Announces Public Certificate Authority for the Post-Quantum Web
date: 2026-09-29
categories: [TECHNOLOGY]
tags: [CLOUDFLARE,CERTIFICATE AUTHORITY,POST-QUANTUM,ENCRYPTION,SECURITY]
---

## Cloudflare Announces Public Certificate Authority for the Post-Quantum Web 🚀

Cloudflare, Inc. (NYSE: NET) today announced its intent to become a public Certificate Authority (CA), an open service that issues the digital certificates websites need to encrypt traffic and prove their identity to visitors. The new CA will support both traditional encryption and next-generation post-quantum Merkle Tree Certificates (MTCs), giving every website a path to stay protected as computing power advances—**with no new tools or rebuilds required**. 

Additionally, Cloudflare has agreed to acquire established, publicly trusted Root CA key material from GlobalSign, which will provide ubiquity across the global Web PKI ecosystem.

Today, that trust is concentrated in a small number of dominant issuers, creating systemic risk if any one of them fails or is compromised. At the same time, most certificate infrastructure was built before quantum computing became a practical concern. Quantum computers capable of breaking today's encryption are expected within years, and much of the web is not prepared for that shift. Matthew Prince, CEO and co-founder of Cloudflare, said, **"Upgrading the web's security before quantum computers can break it is one of the biggest coordination challenges in the history of the Internet."**

To ensure certificates work on older smartphones, operating systems, and devices that no longer receive software updates, Cloudflare plans to acquire an established root certificate. Acquiring one means websites using Cloudflare-issued certificates will be recognized immediately, including on legacy hardware. Cloudflare has also applied for inclusion in the Chrome, Apple, Microsoft, and Mozilla root programs. 

Building on a successful experiment with Chrome, Cloudflare will also begin issuing production MTCs designed around built-in transparency, paving the way for post-quantum security without sacrificing web speed or performance, all from a new, single CA. However, much of this burden rests on a small set of dominant issuers. Cloudflare's new public CA will add an independent, high-scale issuer to that foundation.

Cloudflare will introduce **Glass-Box Operational Transparency**, sharing detailed operational and technical insights, publishing reproducible code builds, and maintaining a live, public health dashboard. **Zero-Downtime Incident Response** will leverage automated renewal signaling (RFC 9773) to seamlessly trigger background certificate replacements across millions of sites instantly, minimizing the risk of mass web outages. 

Scalable post-quantum security will be provided, as MTCs, co-authored by Cloudflare as an IETF draft specification, verify that a certificate is logged in a trusted registry using lightweight proofs, avoiding the need to transmit heavy post-quantum signatures with every connection. 

Cloudflare expects its acquisition of publicly trusted Root CA key material from GlobalSign to close in the next two months. Production MTC issuance is scheduled to begin in the first quarter of 2027, following completion of browser root program application and acceptance process for classical certificates.

[Read full article](https://www.darkreading.com/cloud-security/cloudflare-announces-public-certificate-authority-post-quantum-web)