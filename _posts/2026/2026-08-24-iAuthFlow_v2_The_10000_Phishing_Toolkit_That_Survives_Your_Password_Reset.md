---
title: iAuthFlow v2 The $10,000 Phishing Toolkit That Survives Your Password Reset
date: 2026-08-24
categories: [CYBERSECURITY]
tags: [PHISHING,CYBERCRIME,SECURITY,GOOGLE]
---

## iAuthFlow v2: The $10,000 Phishing Toolkit That Survives Your Password Reset

The **iAuthFlow v2** phishing toolkit utilizes a phished Google session to enroll an attacker-controlled passkey that survives password resets. Abnormal Security researchers have published an analysis of this toolkit, which is sold on a Russian-language cybercrime forum for a base price of **$10,000**. The author also offers additional capability modules for sale separately.

Once the target completes a phishable Google login, the toolkit uses the authenticated session to enroll a passkey controlled by the operator. In the seller's recorded demonstration, the account owner later changes their password, invalidating the active session—but the operator can still authenticate with the newly enrolled passkey and regain access to the mailbox.

The toolkit employs a **browser-in-the-middle attack**. The victim sees what appears to be a real Google login page, while iAuthFlow v2 operates another browser on the attacker's server. Everything the victim types, including their email, password, and two-factor code, is sent to that remote browser, which logs in to Google. In the demo, the fake login page used a trycloudflare.com subdomain, providing a valid TLS certificate and a more trustworthy appearance.

Once the relay gives the attacker's browser Google's session cookies, iAuthFlow v2 holds the target on a "Verification, Processing" page while the toolkit works inside the account. This pause is a named state in the software, not a recording artifact. The session log timestamps tell the story precisely: login at **21:37:18**, passkey created and saved at **21:37:24**—just six seconds to establish persistent access.

The passkey module navigates the target's Google passkey settings through the authenticated browser and requests a new credential. The enrolled passkey is then stored on the attacker's side, and the toolkit records "Passkey created and saved."

This is more serious than simply stealing a session cookie because a password reset does not remove a passkey. A passkey is a separate cryptographic credential linked to the account and remains active until it is manually removed. The demo illustrates the risk clearly: after the victim changes their password, the attacker's session stops working. However, the attacker can choose "Try another way," use the passkey they previously added, and regain access to the mailbox without the victim's knowledge.

The toolkit targets Google in the build Abnormal examined, but the seller advertises versions for Microsoft, iCloud, and LinkedIn. The same post-authentication persistence logic applies wherever passkeys can be enrolled.

Containment after an iAuthFlow v2 compromise requires more than typical incident response measures. Cleanup is particularly crucial with iAuthFlow v2 because neither a password reset nor session revocation removes an attacker-enrolled passkey. Organizations must restore the account only after removing unauthorized authentication methods and other persistence mechanisms. This full sweep should cover unauthorized passkeys, security keys, malicious Gmail filters and forwarding rules, delegated access, OAuth grants, app permissions, and recovery settings. Organizations running Google Workspace can utilize the **Security Investigation Tool** to audit the account before declaring it clean.

[Read full article](https://securityaffairs.com/197748/cyber-crime/iauthflow-v2-the-10000-phishing-toolkit-that-survives-your-password-reset.html)