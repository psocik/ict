---
title: BiDi Swap The bidirectional text trick that makes fake URLs look real
date: 2025-10-28
categories: [RESEARCH]
tags: [SECURITY,URL SPOOFING,BIDI SWAP,PHISHING,CYBERSECURITY]
---

Varonis Threat Labs has highlighted a decade-old vulnerability called BiDi Swap that enables URL spoofing. This technique exploits how browsers handle Right-to-Left (RTL) and Left-to-Right (LTR) scripts to create malicious URLs that appear trustworthy, often used in phishing attacks. The core issue lies in how the Bidirectional (Bidi) Algorithm, a part of the Unicode Standard designed to correctly display mixed LTR and RTL scripts, sometimes struggles with subdomains and URL parameters.

Prior to BiDi Swap, attackers used Punycode Homograph Attacks, utilizing Internationalized Domain Names (IDNs) with non-Latin characters visually similar to Latin letters, to create spoofed domains. Another method involved RTL Override Exploits, embedding Unicode characters (e.g., U+202E) to flip text direction within a string, disguising file extensions or reordering text to conceal malicious file endings. These past attacks demonstrated how subtle nuances in text handling can lead to significant security vulnerabilities, underscoring the need for continuous vigilance.

BiDi Swap allows attackers to craft URLs where LTR subdomains are combined with RTL parameters to mimic legitimate domains. For example, a URL like httpss://varonis.com.ו.קום/ can be created, where the RTL characters can be manipulated to make the URL appear as a legitimate varonis.com subdomain. While Chrome's Navigation suggestion for lookalike URLs provides partial protection, it doesn't flag all domains. Firefox highlights key domain parts in the address bar as a different UI approach. Microsoft Edge was informed of the issue and marked it as resolved, but the URL representation remains unchanged.

To mitigate BiDi Swap risks, it's crucial to verify suspicious URLs, especially those mixing scripts or displaying unexpected patterns. Browser developers should enhance protections like domain highlighting and lookalike detection. End users should be educated to hover over links, confirm SSL certificates, and check domain consistency to avoid falling victim to these attacks. Awareness and caution are key to thwarting potential security risks.

To read the complete article, see: [Bleeping Computer](https://www.bleepingcomputer.com/news/security/bidi-swap-the-bidirectional-text-trick-that-makes-fake-urls-look-real/) 

— Stay safe online! 💻