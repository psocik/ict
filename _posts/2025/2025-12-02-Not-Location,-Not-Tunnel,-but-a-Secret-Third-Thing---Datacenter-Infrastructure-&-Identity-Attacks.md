---
title: Not Location, Not Tunnel, but a Secret Third Thing - Datacenter Infrastructure & Identity Attacks
date: 2025-12-02
categories: [SECURITY]
tags: [DATACENTER,IDENTITY ATTACKS,INFRASTRUCTURE]
---

The amount of identity telemetry that originates from datacenter infrastructure is mind-boggling.  
What do the 10 million authentication events look like when grouped by AS? There’s a power law distribution at play where more than half of those events originate from Microsoft datacenters. The remaining top 10 AS organizations are not surprising and include CloudFlare, Google, ZScaler, Amazon, and a few other heavy hitters.  
One excellent example from my research is Latitude.sh, a bare-metal provider based in Brazil. Latitude leases cloud assets out and accepts anonymous cryptocurrency as payment. This is, of course, attractive for cybercriminals.  
We can safely conclude that some AS have a higher potential for abuse and fraud than other AS based on their country of origin, laws in that country, acceptance of cryptocurrency, and other similar factors. It’s not fair to say that all authentication from a provider like Latitude.sh is malicious all of the time, but it’s defensible to describe it as at least worthy of investigation.  
With this information in hand, I drafted plans to implement a detection system that classifies identity logins from datacenter infrastructure, compares the events to a baseline of previous datacenter activity, and flags authentication from datacenter IPs that belong to an AS with a higher abuse potential.  
By subdividing the problem space, we turned 10 million plus events into a manageable haystack of a few hundred events per day to analyze. To date, we’ve reported over 3,400 instances of datacenter authentication events that met criteria for investigation. Of the 3.4k reports, about 3.2% were rejected. This is a strong performance compared to the baseline of identity detection efficacy, which usually hovers around a 4-5% rejection rate.  

To read the complete article see: [Huntress Article](https://www.huntress.com/blog/datacenter-infrastructure-and-identity-attacks)  
