---
title: Is Your Android TV Streaming Box Part of a Botnet?
date: 2025-11-24
categories: [MALWARE]
tags: [ANDROID TV,BOTNET,SECURITY,KREBS ON SECURITY]
---

On the surface, the **Superbox** media streaming devices for sale at retailers like **BestBuy** and **Walmart** may seem like a steal: they offer unlimited access to more than 2,200 pay-per-view and streaming services like **Netflix**, **ESPN**, and **Hulu**, all for a one-time fee of around $00. But security experts warn these TV boxes require intrusive software that forces the user’s network to relay Internet traffic for others, traffic that is often tied to cybercrime activity such as advertising fraud and account takeovers.

Experts say while these Android streaming boxes generally do what they advertise — enabling buyers to stream video content that would normally require a paid subscription — the apps that enable the streaming also ensnare the user’s Internet connection in a distributed residential proxy network that uses the devices to relay traffic from others.

Censys’s Ashley said the phone home to China’s Tencent QQ instant messaging service was the first red flag with the Superbox devices she examined. She also discovered the streaming boxes included powerful network analysis and remote access tools, such as [Tcpdump](https://en.wikipedia.org/wiki/Tcpdump) and [Netcat](https://en.wikipedia.org/wiki/Netcat).

“This thing DNS hijacked my router, did [ARP poisoning](https://en.wikipedia.org/wiki/ARP%5Fspoofing) to the point where things fall off the network so they can assume that IP, and attempted to bypass controls,” she said. “I have root on all of them now, and they actually have a folder called ‘secondstage.’ These devices also have Netcat and Tcpdump on them, and yet they are supposed to be streaming devices.” 

To read the complete article see: [Full Article](https://krebsonsecurity.com/2025/11/is-your-android-tv-streaming-box-part-of-a-botnet/) 😮