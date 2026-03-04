---
title: Malvertising Threat Actor D-Shortiez Abuses WebKit Back-Button Hijack
date: 2026-03-03
categories: [CYBER SECURITY]
tags: [MALVERTISING,CYBERSECURITY,IOS,SAFARI,SCAMS]
---

## Malvertising Threat Actor D-Shortiez Abuses WebKit Back-Button Hijack in Forced-Redirect Browser Campaign 🚨

A threat actor tracked as **D-Shortiez** has been running a persistent malvertising campaign that turns a WebKit browser behavior into a trap, forcing iOS Safari users into scam pages with no easy way out. The campaign is not entirely new in concept — forced redirect attacks have long been a fixture of the online ad fraud ecosystem — but D-Shortiez has introduced a technical element that sets it apart: a back-button hijack that strips victims of their ability to navigate away once they land on a malicious destination.

Confiant analysts identified D-Shortiez as a group actively running forced redirect campaigns that push victims down malicious click-chains surfacing familiar online scams. Their close examination of the group’s payload revealed that it opens with standard fingerprinting and tracking functions. However, what drew the researchers’ attention was the redirect mechanics itself, specifically a nested try/catch block beginning at line 211, which handles the actual forced redirection by firing multiple redirect attempts simultaneously. The scale of this campaign is significant. Over the last six months, D-Shortiez has served more than **300 million** malicious ad impressions, targeting US audiences most heavily, with reach extending into Canada and across parts of Europe. The iOS platform has been the primary target.

The most technically distinctive aspect of this campaign is how D-Shortiez exploits the browser’s popstate event to prevent victims from navigating away from scam pages on Safari. The payload uses `window.top.history.pushState()` to insert a fake entry into the browser’s session history stack. An `onpopstate` event handler bound to `window.top` then catches any back-button press and redirects the user to the scam URL — appending a “back” parameter — instead of returning them to the legitimate page they left behind. On iOS, the script worked exactly as intended — effectively locking the back button and keeping victims stuck on scam pages with no clean route out.

The vulnerability was disclosed to Apple on **September 29**, and Apple patched it through a Safari security update issued on **January 23**, identified as **HT213600**. iOS and Safari users who have not yet applied this update remain directly exposed to this back-button hijack. All iOS and Safari users should install Apple’s security update HT213600 without delay to eliminate this specific vulnerability from their devices. Security and ad operations teams should audit their ad supply chains for redirect-based payloads and block all known D-Shortiez IOC domains at the DNS and network level. These IOCs span a wide network of wildcard subdomains across extensions including .shop, .site, .homes, .beauty, .skin, .boats, .cyou, and several other top-level domains.

[Read full article](https://cybersecuritynews.com/malvertising-threat-actor-d-shortiez-abuses-webkit-back-button/)