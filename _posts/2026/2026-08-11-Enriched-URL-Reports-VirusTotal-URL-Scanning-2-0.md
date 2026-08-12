---
title: Enriched URL Reports VirusTotal URL Scanning 2.0
date: 2026-08-11
categories: [SECURITY]
tags: [VIRUSTOTAL,URL SCANNING,SECURITY,ANALYSIS]
---

## Enriched URL Reports - VirusTotal URL Scanning 2.0

🚀 **Traditional URL analysis has been redefined!** The launch of **URL Scanning 2.0** significantly expands VirusTotal's URL analysis capabilities by introducing automated visits with a full browser instance and deeper historical visibility. Instead of relying solely on static reputation scores, URL Scanning 2.0 enriches reports with "under-the-hood" headless browser telemetry, including the DOM, full-page screenshots, web technologies, and network request logs. 

🔍 **Key Features:**
- **Historical Analysis Pivoting:** Track how a page has changed over time.
- **Rich Telemetry:** Every scan generates granular telemetry that provides a blueprint of the target page's execution.
- **Headless Browser Data:** Includes full-page visual screenshots, full DOM trees, and web technologies (e.g., Cloudflare, PHP, HTTP/3).
- **Page and Network Statistics:** Detailed counters of individual network requests, encrypted HTTPS transactions, unique contacted domains/subdomains, and serving IP address mappings with geographic tracking.
- **Anti-Phishing Fingerprints:** Automatic identification of brands, cloned-website tags, password input fields, tracker IDs, and favicon dhashes.

📈 **For Paid Customers:**
VirusTotal customers unlock deeper retrospective capabilities and exclusive data fields. Analysts can review full historical analyses of a URL as observed at specific points in time and access advanced telemetry like full DOM captures of the execution. 

🔗 **Dynamic Information:**
The information within report tabs dynamically re-renders to match the exact historical state of the snapshot selected. Analysts will find HTTP transactions, detected JavaScript variables, console messages, external outbound links, and other critical metadata. These key technical markers serve as pivotable and searchable attributes, allowing teams to conduct advanced footprint hunting and instantly find other malicious URLs exhibiting the same technical fingerprint.

🕵️‍♂️ **Example Discovery:**
During the analysis of a financial phishing site, researchers discovered the page relied on static assets hosted on a third-party domain. This finding demonstrated a multi-brand operation, allowing analysts to map out a highly segmented subdomain tree used for hosting assets, capturing payments, and backend control panels.

🌐 **Conclusion:**
URL Scanning 2.0 represents a paradigm shift in how security analysts investigate web-based threats. Investigations are no longer limited to static verdicts. By surfacing powerful metadata directly inside the workflow, analysts can now turn a single indicator into a comprehensive infrastructure map.

[Read full article](https://blog.virustotal.com/2026/08/enriched-url-reports-url-scanning-20.html)