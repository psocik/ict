---
title: Most Wanted The Phishing Kits and Techniques Getting Past Security Controls
date: 2026-11-26
categories: [CYBERSECURITY]
tags: [PHISHING,SECURITY,MALWARE,CYBERSECURITY,ATTACKS]
---

## Most Wanted: The Phishing Kits and Techniques Getting Past Security Controls

Every phishing attack has to get past email security, web filtering, and safe browsing before it reaches an employee. Some kits manage that far more often than others, and those are the kits that security teams need to know about. At Push Security, we measure this as **breakthrough rate**: the share of attacks that get past email security, web gateways, and safe browsing to reach the user. 

### Key Points:
- **Email Security:** Half of the attacks we see never touch email. The lure arrives through a search ad, a chat message, social media, a calendar invite, or a QR code. The rest come from trusted senders and services, so they pass reputation checks.
- **Web Gateways:** The pages sit on trusted hosting and are assembled in the browser. The domains rotate every few days, so reputation data lags behind them.
- **Safe Browsing and Scanners:** Bot checks and cloaking show scanners a harmless page. A new domain isn't on any blocklist yet.

When the page loads in the user's browser and the user interacts with it, that's a breakthrough. Breakthrough rate counts those attacks, not attempts.

From August to October 2026, one kit ranked first by breakthrough rate every month. **DOMDIFFER**, an AiTM phishing kit that targets corporate Google and Microsoft accounts, broke through 2-4x as often as the next kit each month. DOM mirroring, the mechanism it uses under the hood, also happens to be the newest and fastest-growing way for a kit to relay a sign-in. We first saw DOMDIFFER in February 2026. We believe it grew out of NakedPages, a reverse proxy kit, and the two kits share infrastructure in several places. DOMDIFFER went quiet in the spring, came back over the summer, and has held the top rating since August. Most of its detections in that time came from fake calendar event lures. One real DOMDIFFER attack starts with a fake Google Voice notification about a new voicemail. The link passes a bot check that turns scanners away. The victim then sees what looks exactly like Google's sign-in page. It isn't a screenshot or a static copy. It's Google's real page, mirrored from the attacker's browser.

In DOM mirroring, the attacker's own browser does the real sign-in. It sends the page's structure (the DOM) to the victim's browser, which rebuilds a working copy. Because a real browser does the sign-in, the kit sends Google genuine browser signals and handles new sign-in steps without needing extra code. Replica pages are still the most common class, but DOM mirroring is the newest and the fastest growing in 2026. Laurseraph, the main criminal pixel-streaming kit, has switched to DOM mirroring, and kits such as BlueKit and PhantomDOM use it too. 

**Passkeys** are worth rolling out, and they stop AiTM phishing where they're enforced. But AiTM is now one payload among several, and attackers are getting creative with how they combine them. Kits use AiTM interchangeably with payloads that passkeys don't touch. In authorization attacks such as device code phishing, the victim signs in on Microsoft's real page and grants the attacker access. Other kits skip the sign-in page altogether and trick the victim into installing a remote access tool instead. Kits pick the payload to match the visitor. A Windows visitor might get a remote access tool, a Microsoft account device code phishing, and a Google account AiTM.

[Read full article](https://thehackernews.com/2026/11/most-wanted-phishing-kits-and.html)