---
title: A Coordinated Response to MadeYouReset HTTP/2 Protocol Attacks
date: 2025-08-13
categories: [RESEARCH]
tags: [HTTP/2,SECURITY,CYBERSECURITY,DDOS,VULNERABILITY]
---

A new attack on the HTTP/2 protocol, called MadeYouReset, has been disclosed and published. Akamai's own implementation of HTTP/2 is not vulnerable to this attack, but we believe it's useful to discuss the context and vulnerability in some detail. In 2023, many server operators on the internet encountered a zero-day vulnerability called HTTP/2 Rapid Reset (CVE-2023-44487) that cybercriminals had exploited to launch massive Layer 7 distributed denial-of-service (DDoS) attacks. In the newest iteration of this attack, the client sends deliberately invalid control messages. It knows that the specification requires servers to reset the stream if they encounter such invalid messages — hence the name MadeYouReset. And once the server has reset the stream, the client is free to open another one, even if it hasn’t actually received the server’s reset yet. It’s worth noting that no live attacks attempting to exploit this new vulnerability have been observed. The attack vector was discovered by security researchers at Tel Aviv University, reported to Akamai via our bug bounty program, and a response was simultaneously coordinated by CERT before any disruption could occur. 

To read the complete article see:

[Full Article](https://www.akamai.com/blog/security/response-madeyoureset-http2-protocol-attacks) 
