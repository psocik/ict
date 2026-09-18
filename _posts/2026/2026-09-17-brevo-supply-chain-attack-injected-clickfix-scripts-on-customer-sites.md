---
title: Brevo Supply-Chain Attack Injected ClickFix Scripts on Customer Sites
date: 2026-09-17
categories: [SECURITY]
tags: [BREVO,MALWARE,CLOUDFLARE,SECURITY,WORDPRESS]
---

## Brevo Supply-Chain Attack 🚨

Brevo confirmed that attackers stole a Cloudflare API key and used it to inject malicious ClickFix scripts into its websites and JavaScript files embedded on customer sites to distribute malware. The customer relationship management and digital marketing company states that the attackers used the API key to create a malicious Cloudflare Worker that modified content at the CDN edge for approximately five and a half hours on September 14.

### Impacted Sites 🌐
The attack affected pages on:
- brevo.com
- sendinblue.com
- login/account/my/onboarding.brevo.com
- sibforms.com

The Cloudflare worker also modified the Brevo forms script, Brevo Conversations widget, and the Brevo SDK loader scripts that customers embed on their websites. Brevo explained that attackers obtained a long-lived Cloudflare API key with full account permissions that had been hardcoded in application source code. This allowed them to create Cloudflare Workers, routes, and DNS records across Brevo's zones without triggering an alert.

### Detection and Response 🔍
"Because the Worker rewrote responses at the edge and removed security headers such as Content-Security-Policy, our origin servers and files remained unmodified, and standard integrity checks did not detect the change," explained Brevo. Upon detecting the compromise, Brevo removed the Worker and its routes, defining the exposure window as between 16:07 and 20:30 UTC.

### Scope of the Incident 📊
The incident was first reported by security firm Sansec, which noted that it may have impacted up to 100,000 websites using the affected Brevo components. Sansec confirmed that all malicious subdomains stopped resolving on September 15, and Brevo files are now clean. Visitors to these websites were shown a fake Cloudflare verification page, followed by ClickFix instructions urging them to run a command on Windows.

### WordPress Vulnerability ⚠️
On WordPress websites embedding an affected Brevo widget, the script checked whether the visitor was logged in as an administrator and attempted to upload a malicious plugin from a redacted URL. BleepingComputer found the archive uploaded to VirusTotal and confirmed it pretends to be a WordPress plugin named "Web Media Optimizer" but acts as a persistent backdoor and JavaScript loader.

### Recommendations ✅
WordPress administrators who visited an affected site while logged in on September 14 should check for unusual plugins installed or activated that day and remove them. If found, they should also rotate administrator passwords.

For more details, [Read full article](https://www.bleepingcomputer.com/news/security/brevo-supply-chain-attack-injected-clickfix-scripts-on-customer-sites/).