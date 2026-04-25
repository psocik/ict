---
title: Application Control Bypass for Data Exfiltration
date: 2026-03-31
categories: [CYBERSECURITY]
tags: [DATA_EXFILTRATION,CYBERSECURITY,FIREWALL,SECURITY_ASSESSMENT]
---

## Application Control Bypass for Data Exfiltration

In case of a cyber incident, most organizations fear more data loss (via exfiltration) than regular data encryption because they have a good backup policy in place. If exfiltration happens, it means a total loss of control of the stolen data with all the consequences (PII, credit card numbers, etc.).

While performing a security assessment of a corporate network, I discovered that a TCP port was open to the wild Internet, even though the audited company has a pretty strong firewall policy. I attempted to exfiltrate data through this port, and while it worked, the data transfer failed after approximately 5KB of data sent... weird! Every time, the same situation occurred. I spoke to a local Network Administrator who mentioned that they have a Palo Alto Networks firewall in place with App-ID enabled on this port.

**Note:** What I am explaining here is not directly related to this brand of firewall. The same issue may apply with any "next-generation" firewall! App-ID in Palo Alto Networks firewalls is the component performing traffic classification on the protected network(s), regardless of port, protocol, or encryption. Instead of relying on traditional port-based rules (e.g., TCP/80 == HTTP), App-ID analyzes traffic in real-time to determine the actual application (e.g., Facebook, Dropbox, custom apps), enabling more granular and accurate security policies.

The main issue with this technique is that enough packets must be sent over the wire to perform a good classification. So, the traffic is always allowed first and, if something bad is detected, remaining packets are blocked.

In terms of data volume, there's no strict fixed threshold, but in practice, App-ID usually needs at least the first few KB of application payload to reach a reliable classification. Roughly speaking: <1 KB (or just handshake packets) is almost always insufficient; ~1-5 KB allows basic identification for simple or clear-text protocols (HTTP, DNS, some TLS SNI-based detection); and ~5-10+ KB offers much higher confidence, especially for encrypted or complex applications. That's why my attempts to exfiltrate data were all blocked after ~5KB.

To bypass this, a scenario was developed: On the external host, a netcat in an infinite loop with a small timeout was executed. On the victim's computer, a Python script was then used to read a file, split it into chunks of 3KB, and send everything to a TCP connection (with retries in case of failure, of course). The file was successfully exfiltrated, with the SHA256 hashes being identical. This technique, while slow, does not generate peaks of bandwidth that could reveal a huge amount of data being exfiltrated! It is more of a proof-of-concept because firewalls may implement more detection controls. For example, this technique is easy to detect due to the high number of small TCP connections that may look like malware beaconing.

[Read full article](https://isc.sans.edu/forums/diary/Application%20Control%20Bypass%20for%20Data%20Exfiltration/32850/)