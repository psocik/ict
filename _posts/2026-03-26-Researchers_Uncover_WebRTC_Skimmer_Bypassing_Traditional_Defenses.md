---
title: Researchers Uncover WebRTC Skimmer Bypassing Traditional Defenses
date: 2026-03-26
categories: [SECURITY]
tags: [WEBRTC,SKIMMER,SECURITY,MALWARE,DATA-THEFT]
---

## Researchers Uncover WebRTC Skimmer Bypassing Traditional Defenses 🚨

Researchers have discovered a new skimmer that utilizes **WebRTC** to steal and send payment data, effectively bypassing traditional security controls. Sansec researchers revealed that this payment skimmer employs WebRTC data channels instead of standard web requests to load malicious code and exfiltrate stolen payment data.

> "What sets this attack apart is the skimmer itself. Instead of the usual HTTP requests or image beacons, this malware uses WebRTC DataChannels to load its payload and exfiltrate stolen payment data," reported Sansec. This marks the first instance where Sansec has observed WebRTC being used as a skimming channel.

This innovative technique allows the skimmer to evade standard security defenses, making detection significantly more challenging compared to traditional skimmers. The researchers highlighted that WebRTC connections are not governed by standard **Content Security Policy** rules, enabling attackers to bypass protections even on secure sites. With limited support for WebRTC-specific controls, many sites remain vulnerable.

Additionally, WebRTC employs encrypted **UDP** traffic rather than **HTTP**, complicating the detection of stolen data by network security tools.

The attack specifically targeted a car maker's e-commerce site by exploiting the **PolyShell** vulnerability in **Magento** and **Adobe Commerce**, which permits attackers to upload malicious files and execute code without authentication. Since **March 19, 2026**, this flaw has been widely exploited, with scanning from over 50 IPs and attacks impacting more than half of the vulnerable stores.

The skimmer operates as a self-executing script that establishes a WebRTC connection to a hardcoded attacker server ("202.181.177[.]177" over UDP port 3479), circumventing traditional web controls. It forges the entire connection setup locally, eliminating the need for a signaling server, and directly connects to the attacker's IP over an encrypted DataChannel.

Once connected, it receives malicious JavaScript in chunks, stores it, and executes it when the connection closes or after a brief delay. To further evade defenses, it steals a valid **CSP nonce** from existing scripts and uses it to inject the payload, bypassing strict security policies. The payload operates quietly during browser idle time, minimizing detection risk and enabling attackers to inject code into the page to steal sensitive data such as payment information.

The report concludes, "The traffic itself is also harder to detect. WebRTC DataChannels run over **DTLS-encrypted UDP**, not **HTTP**. Network security tools that inspect HTTP traffic will never see the stolen data leave," and it also provides **Indicators of Compromise (IoCs)**.

To read the complete article see:
[Read full article](https://securityaffairs.com/190002/malware/researchers-uncover-webrtc-skimmer-bypassing-traditional-defenses.html)