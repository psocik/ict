---
title: Fake Amazon Music x YouTube Deal Lures Creators into a Google Login Trap
date: 2026-10-21
categories: [CYBERSECURITY]
tags: [AMAZON,YOUTUBE,PHISHING,SECURITY,CREATORS]
---

## Fake Amazon Music x YouTube Deal Lures Creators into a Google Login Trap 🚨

A wave of sites is offering YouTube creators what looks like an invite-only advertising deal with Amazon Music. These sites show creators their channel stats, then ask them to "verify" their channel with Google before revealing a personalized offer. This verification step is a phishing attempt designed to steal Google sign-in details, putting the creator's account and YouTube channel at risk. If you receive one of these offers, **do not enter your Google password or verification codes**. If you already have, secure your Google account immediately! 🔒

The site, hosted at `amazonyt[REDACTED BY DNB EDITOTS TO GET PAST GOOGLE FILTERS]`, calls itself the "Amazon Artists Music -- Creator Portal." It promises **advertising collaborations with Amazon and Amazon Music**, and describes the program as invitation-only. There is also an earnings calculator. Once a YouTube channel link is pasted, a dashboard displays real channel data: subscriber count, total views, and recent uploads. Seeing your own data on an Amazon-branded page makes the offer feel tailored to you. To pull this data, the site queries YouTube's own public API directly from your browser. The offer itself stays locked until users "verify" their channel by clicking a "Continue with Google" button. This action opens a full-screen frame loading content from a second domain, `youtubechannelverification[REDACTED BY DNB EDITOTS TO GET PAST GOOGLE FILTERS]`. The second-stage code is designed to send the email address, password, and multi-factor authentication (MFA) challenges to its own server. It is built to collect not just the password but also verification codes, helping criminals bypass additional account protection.

After submitting credentials, victims are often returned to a "success" page on `amazonyt[REDACTED BY DNB EDITOTS TO GET PAST GOOGLE FILTERS]`, where the offer is unlocked and a "Request received" confirmation displayed. This reassuring ending may give criminals more time before victims suspect anything. This campaign stands out because password collection happens on a second domain, `youtubechannelverification[REDACTED BY DNB EDITOTS TO GET PAST GOOGLE FILTERS]`, and the success page is designed to evade suspicion. Personalization is automatic; every visitor gets a dashboard and offer built from their own channel's real numbers. YouTube creators are a long-standing target, as a hijacked channel provides criminals with a trusted audience for reaching potential victims.

### How to Spot a Fake Sponsorship Offer
- Treat "verify your channel" requests with caution; Google passwords and verification codes belong on Google's genuine sign-in page, `accounts.google.com`. 
- Always check the domain, not the logo; verify any offer independently through its official website.
- If details were entered, immediately change your Google password. Review devices, sign out of unfamiliar sessions, and remove unrecognized third-party apps. If an MFA code was entered, treat the account as potentially compromised. In YouTube Studio, check Settings > Permissions for unauthorized users, and if access is lost, follow YouTube's guidance for recovering a hacked channel.

For more information, [Read full article](https://www.malwarebytes.com/blog/threat-intel/2026/10/fake-amazon-music-x-youtube-deal-lures-creators-into-a-google-login-trap)!