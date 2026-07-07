---
title: Opera GX Flaw Lets Sites Auto-Install Mods to Steal Data
date: 2026-07-06
categories: [SECURITY]
tags: [OPERA,BROWSER,SECURITY,VULNERABILITY]
---

## Opera GX Flaw: A Serious Security Risk 🚨

A critical flaw discovered in the **Opera GX** browser could enable malicious websites to automatically install a customization mod and use it to steal data from other sites a victim visited, with no user interaction required. 

**GX Mods** allow Opera GX users to customize the browser's appearance, sounds, and look of websites. Unlike normal extensions, they carry no permissions and cannot run JavaScript. An independent security researcher, operating under the moniker **zhero_web_security**, found that a mod installs automatically, without any permission prompt, as soon as its file is downloaded. This means an attacker could plant one just by loading a hidden frame pointing to it. 

Because a mod's styling is applied to every page and tab, the attacker's CSS was injected across every website the victim opens. Ordinary CSS injection is usually confined to a single page, but this allowed the attacker to gain a foothold across the entire browser. 

CSS cannot read a page's contents directly, but it can be crafted to trigger network requests based on what a page contains, enabling data exfiltration piece by piece. Using that, the researcher built a **zero-click cross-site leak**, or **XS-Leak**, that recovered a victim's full Gmail address after a silent redirect to a Google account page. They noted the method is not limited to email addresses. That same auto-install behavior also enabled a **denial-of-service (DoS)** attack against both Opera and Opera GX. 

Because Chromium-based browsers block extensions in private windows, forcing a mod to install in **Incognito mode** caused the browser to crash and wipe the user's open tabs. Any file with a **.crx** extension triggered it, whether or not it was a real mod. 

The researchers reported the flaw in February through Opera's **Bugcrowd** bug bounty program. It was initially triaged as a low-priority issue, but Opera's security team reassessed it as critical. It was patched on **May 8** and a **$5000** bounty payment was awarded. The research was published on **July 3** as a proof of concept (PoC) and the work was tested on Opera GX version **127.0.5778.41**, after the fix had shipped.

For more details, check out the full article here: [Read full article](https://www.infosecurity-magazine.com/news/opera-gx-flaw-gx-mods-css/)