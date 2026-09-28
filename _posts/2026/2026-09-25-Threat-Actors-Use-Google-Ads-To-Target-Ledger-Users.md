---
title: Threat Actors Use Google Ads To Target Ledger Users
date: 2026-09-25
categories: [CYBERSECURITY]
tags: [GOOGLE,ADS,LEDGER,PHISHING,SECURITY]
---

## Threat Actors Use Google Ads To Target Ledger Users 🚨

In August 2026, Zscaler ThreatLabz analyzed a phishing campaign that used fraudulent Google ads to target Ledger hardware wallet users. The ads redirected users through Google Cloud Storage and Vercel to a Google Sites page containing a phishing page impersonating Ledger in an iframe. During our analysis, the Vercel redirect appeared to change every 15-20 minutes. There, a fake device-verification process prompted users to enter their secret recovery phrases, which attackers could use to access their wallets without the physical devices. Additionally, the fraudulent Google ads targeting Ledger users appeared under a Google-verified advertiser profile.

### Key Findings 🔍
- ThreatLabz observed malicious sponsored ads in search results for Ledger-related terms.
- The ads targeted users in the United States, Europe, and parts of Asia.
- The ad displayed `google.com` and claimed "10L+ visits in the past month", which may have made the ad look more credible.
- The ad came from a long-standing, verified advertiser account with no observed history of malicious ads, suggesting the threat actor may have compromised the account to run the campaign.

Clicking the malicious ad took users to a Google Cloud Storage URL, which redirected them to a Vercel-hosted page. That page then redirected users to a Google Sites page displaying the phishing page in an iframe. The attack also used Vercel-hosted domains to serve the phishing content displayed in the iframe. The Vercel domain in the JavaScript redirect appeared to change approximately every 15-20 minutes during our analysis, making the activity harder to detect based on the reputation of the domain.

### Phishing Page Details 💻
The phishing page mimicked the official Ledger interface and offered downloads for Windows, macOS, Linux, and mobile devices. The phishing page collected device metadata and monitored user interactions like keypresses, touches, and mouse movements. It sent this data to a Vercel-hosted endpoint, potentially allowing attackers to distinguish real visitors from automated analysis tools. The phishing page also included a Cloudflare Web Analytics beacon (`beacon.min.js`) configured with an analytics token.

After selecting a device, the user was presented with messages such as "*Connecting your Ledger*" and "*Initializing Firmware Update*." The phishing page then claimed that the Ledger device was connected and asked the user to confirm device ownership. Subsequently, the phishing page prompted the user to enter their secret recovery phrase. A secret recovery phrase (SRP) allows a user to restore a cryptocurrency wallet. By stealing this phrase, attackers can restore the wallet in compatible software and transfer funds without access to the victim's physical Ledger device. The phishing page retrieves the 2,048-word BIP-39 English wordlist from `api/bip39-english.txt` and uses it to provide autocomplete.

For more detailed information, you can read the full article here: [Read full article](https://www.zscaler.com/blogs/security-research/threat-actors-use-google-ads-target-ledger-users) 
