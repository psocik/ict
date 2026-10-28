---
title: GoAhead TLS Flaws Allow Revoked Client Certificates and Enable Session Decryption
date: 2026-10-27
categories: [SECURITY]
tags: [TLS,SECURITY,VULNERABILITIES,GOAHEAD]
---

## GoAhead TLS Flaws Allow Revoked Client Certificates and Enable Session Decryption 🚨

The GoAhead embedded web server has a significant flaw that allows revoked client certificates to bypass login on affected setups. This issue arises because the server loaded a certificate revocation list into its default TLS backend but never activated revocation checking. As a result, a revoked client certificate can still pass authentication.

### Key Details:
- **Affected Builds:** This flaw is present in builds using the OpenSSL backend with mutual-TLS, where both the server and client check each other's certificates.
- **Impact:** A client with a revoked certificate, such as a stolen or retired device, can complete the handshake as if the certificate were still valid, gaining access to resources allowed by that identity.
- **Exploitation Requirements:** For exploitation, the build must use the OpenSSL backend with client certificates required, a trusted certificate authority bundle, issuer checking enabled, and a configured revocation list. The attacker must possess a certificate signed by a trusted authority and listed as revoked.
- **CVE Identifier:** CVE-2026-115881, rated 9.1 by EmbedThis.

### Additional Vulnerabilities:
Researchers have identified two more issues tied to specific TLS builds:
1. **Mbed TLS Problem:** This issue only affects sessions if the client accepts a flawed setup. Clients lacking a minimum-size check may accept it, allowing anyone who recorded the traffic to deduce the key and decrypt the session. TLS 1.3 and ECDHE sessions remain unaffected.
2. **LibreSSL Problem:** An attacker can present a certificate chain longer than GoAhead's 10-certificate limit, completing the handshake as an authenticated client without a trusted key. This occurs only on builds linked against older LibreSSL versions where client certificates are required with issuer checking disabled.

### GoAhead 6.1.1 Release:
The GoAhead 6.1.1 release, made available to device makers on August 2, 2026, and publicly published on October 12, addresses 11 advisories in total, three of which are rated critical. One critical issue involves a login bypass where an attacker can sign in with any password if the user's stored password is in the newer Blowfish format, introduced in version 6.1.0. EmbedThis recommends ending active sessions, restarting the server, and changing Blowfish-stored passwords after upgrading.

### Conclusion:
As of October 27, no reports indicate that these vulnerabilities have been exploited in attacks. For further details, you can read the full article here: [Read full article](https://thehackernews.com/2026/10/goahead-tls-flaws-allow-revoked-client.html)