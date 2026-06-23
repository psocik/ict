---
title: 29-Year-Old Squid Proxy Bug 'Squidbleed' Can Leak Cleartext HTTP Requests
date: 2026-06-22
categories: [SECURITY]
tags: [SQUID,PROXY,SECURITY,VULNERABILITY]
---

## Overview

A **heap over-read** in the Squid web proxy can leak another user's cleartext HTTP request, including any credentials or session tokens it carries, to anyone already allowed to send traffic through the same proxy. This bug traces back to a **1997 FTP-parsing change** and remains active in Squid's default configuration. Researchers at Calif.io disclosed it in June and named it **Squidbleed** (CVE-2026-47729), after **Heartbleed**, which leaked memory in a similar manner. 

## Details

Squid describes this as an attack by a trusted client: someone already permitted to use the proxy, not just any random host on the internet. The leak only affects traffic that Squid can read, specifically cleartext HTTP and TLS-terminating setups where Squid decrypts and inspects. The attacker also needs the proxy to reach an FTP server they control on port 21, which is enabled by default.

The bug resides in Squid's FTP directory-listing parser. If the attacker's FTP server sends a listing line that ends right after the timestamp, with no filename, `copyFrom` lands on the string's null terminator. This causes `strchr` to treat that terminating NUL as part of the string it searches, resulting in a pointer instead of NULL, and the loop never stops. It walks off the end of the buffer, and `xstrdup` copies whatever follows back to the attacker as a filename. Squid reuses freed memory buffers without zeroing them, so a 4KB buffer that recently held a victim's HTTP request still retains most of it. 

Calif's demo pulls an **Authorization header** from a victim sharing the same proxy, which is enough to act as that user. Proof-of-concept code is public, and no in-the-wild exploitation has been reported as of now.

## Recommendations

If you patch, ensure to verify the fix, not just the version. Confirm the guard is in **FtpGateway.cc**, or check your distribution's backport, as distros ship their own builds (Debian packages Squid 5.7). The public thread is still inconsistent: maintainer Amos Jeffries initially stated that Squid 7.6 carried the fix, then corrected that to 7.7. On June 22, Debian's Salvatore Bonaccorso noted that the referenced commit appears to already be in 7.6. 

The fix is small, involving a null-terminator check before the vulnerable `strchr` calls, merged to the development branch in April and v7 in May. The cleaner move, which the researchers recommend, is to **turn FTP off**. Chromium dropped FTP years ago, and most networks carry almost none of it, so disabling it removes this attack surface for free, regardless of the build you run. 

SUSE rates the vulnerability as moderate, CVSS 6.5, and the vector explains the score: the attacker needs proxy access (low privileges), and the only impact is confidentiality, with no effects on integrity or availability. Calif credits **Anthropic's Claude Mythos Preview**, the model behind Project Glasswing, with quickly identifying the `strchr` quirk, similar to other buried parser bugs AI agents have surfaced elsewhere, including in FFmpeg.

For more details, check out the full article: [Read full article](https://thehackernews.com/2026/06/29-year-old-squid-proxy-bug-squidbleed.html)