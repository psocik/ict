---
title: Hackers Obtain Counterfeit TLS Certificates for Google and Other Large Services
date: 2026-10-06
categories: [SECURITY]
tags: [HACKERS,TLS,CERTIFICATES,GOOGLE,SECURITY]
---

## Hackers Obtain Counterfeit TLS Certificates for Google and Other Large Services

🚨 **Breaking News:** Attackers have hijacked three top-level domains and used their control to mint counterfeit TLS certificates for Google and other large organizations, as reported by Google on Tuesday. 

### What Happened?
The attackers launched a series of attacks on the .gh, .sl, and .as country code top-level domains (ccTLDs) and modified authoritative DNS records for selected domains within those namespaces. By controlling these DNS records, they were able to pass automated domain control validation checks and obtain unauthorized certificates for several Google domains and other leading global brands.

### Implications of the Attack
TLS certificates are crucial for authentication and encryption protections for websites, mail servers, and other Internet infrastructure. Unauthorized possession of these certificates allows attackers to impersonate the affected infrastructure. Google has since updated Chrome to block all identified unauthorized certificates and worked with issuing certification authorities to ensure their revocation.

### Recommendations for Domain Owners
Google advises domain owners to:
- Monitor certificate transparency logs for unexpected certificate issuance.
- Publish restrictive Certification Authority Authorization DNS records to prevent attackers from reusing cached validation data after DNS control is restored.

### Conclusion
While Chrome has taken steps to block unauthorized certificates, Google warns that browser-side interventions should not be solely relied upon to protect users. The complexity of DNS hijacks means that undiscovered certificates may still pose a threat.

For more details, read the full article here: [Read full article](https://arstechnica.com/security/2026/10/hackers-obtain-counterfeit-tls-certificates-for-google-and-other-large-services/) 
