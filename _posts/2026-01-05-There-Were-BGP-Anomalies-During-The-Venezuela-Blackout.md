---
title: There Were BGP Anomalies During The Venezuela Blackout
date: 2026-01-05
categories: [RESEARCH]
tags: []
---

Cloudflare Radar's route leak data for AS8048 on January 2nd had some interesting anomalies: 8 prefixes (blocks of IP addresses) were being routed through CANTV, with Sparkle (an Italian transit provider) and GlobeNet (a Colombian carrier) in the Autonomous System (AS) path.

There was also a noticeable spike in BGP announcements in the days leading up to the events and a drastic dip in the "Announced IP Address Space" according to the same Cloudflare Radar data, although it's unclear what this indicates.

When BGP traffic is being sent from point A to point B, it can be rerouted through a point C. If you control point C, even for a few hours, you can theoretically collect vast amounts of intelligence that would be very useful for government entities. The CANTV AS8048 being prepended to the AS path 10 times means there the traffic would not prioritize this route through AS8048, perhaps that was the goal? There are many unanswered questions.

[Read the complete article here](https://loworbitsecurity.com/radar/radar16/) 
