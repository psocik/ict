---
title: 15-Year-Old strongSwan Flaw Lets Attackers Crash VPNs via Integer Underflow
date: 2026-03-30
categories: [SECURITY]
tags: [STRONGSWAN,VPN,SECURITY,VULNERABILITY]
---

## Major Vulnerability in strongSwan VPNs 🚨

A **15-year-old flaw** in strongSwan's EAP-TTLS plugin could allow hackers to knock VPNs offline. Research from **Bishop Fox** reveals how a simple math error leads to massive memory corruption and service collapse. For over a decade and a half, a quiet but serious security flaw has been sitting inside strongSwan, a popular open-source software used by businesses to run their VPNs. This weakness, which dates back to versions from 15 years ago, could allow an outsider to knock a company's entire secure network offline.

The vulnerability was recently detailed by the research firm Bishop Fox. This report followed an official advisory from strongSwan released on **March 23, 2026**, regarding a bug tracked as **CVE-2026-25075**, which impacts nearly every version of the software between 4.5.0 and 6.0.4. The problem lies with a mathematical error known as an **integer underflow**.

In strongSwan's case, the software expects an 8-byte header, and if a hacker sends a tiny message, say only 1 byte, the software still tries to subtract 8 from it. Because of how computer logic works, subtracting a large number from a smaller one does not always result in a negative number and may wrap around to a huge positive value. This calculation causes the server to trigger **malloc**, the system's way of allocating memory, to try and reserve an impossible **18 exabytes** of space, far more than any server actually has.

What makes this discovery particularly interesting is that the VPN might not crash the moment it gets hit, creating what feels like a **ghost in the system**. According to researchers, "the actual 'Blue Screen' or daemon crash happens later when a second connection is made." Further probing revealed a two-step disaster. The first malicious message enters and confuses the server's memory management, known as the **heap**. The server keeps running for a short time, but the next person who tries to connect triggers the actual collapse of the **charon daemon**, the background engine that keeps the VPN alive. This delay makes it incredibly difficult for IT teams to trace the crash back to the original attack.

For an attack to work, several conditions must be met. The server must be running a vulnerable version, have the EAP-TTLS plugin enabled, and be configured to accept **IKEv2 connections**. If your company uses these settings, the fix is relatively simple but urgent; you should upgrade to version **6.0.5** or higher immediately to close the loophole. Bishop Fox has also developed a testing tool that triggers the math error without actually crashing the server, allowing admins to see if they are at risk without losing their connection. If you do not need the EAP-TTLS feature at all, experts suggest turning that plugin off to keep you safe.

[Read full article](https://hackread.com/strongswan-flaw-attackers-crash-vpn-integer-underflow/)