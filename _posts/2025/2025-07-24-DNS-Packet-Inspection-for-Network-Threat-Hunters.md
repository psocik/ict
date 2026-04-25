---
title: DNS Packet Inspection for Network Threat Hunters
date: 2025-07-24
categories: [RESEARCH]
tags: [DNS,THREAT HUNTING,NETWORK SECURITY]
---

## Introduction

When we as network threat hunters think of Command and Control (C2) over DNS, a familiar image comes to mind: long, garbled subdomains streaming out of a network. This being the case, when these channels operate for any significant period of time, they tend to accumulate a substantial amount of “unusual” subdomains.

So when we look at DNS traffic on our networks and encounter some unheard-of domain, let’s say xx1-derp.com, with thousands of unique, encoded subdomains, we can be sure we’ve found something suspicious. Indeed, this is how RITA and AC-Hunter make quick work of identifying C2 over DNS communication on our network.

This “easy to spot” pattern is a consequence of the fact that DNS, by its nature, is not designed for high-bandwidth data transfer. So when threat actors perform activities requiring the transfer of relatively large amounts of data – say exfiltrate a file – then the C2 agent has to chunk the data into countless small pieces, encoding each one as a subdomain in a DNS query. The result is a noisy, conspicuous pattern that’s hard to miss against the backdrop of normal DNS traffic.

To read the complete article see: [https://www.activecountermeasures.com/dns-packet-inspection-for-network-threat-hunters/](https://www.activecountermeasures.com/dns-packet-inspection-for-network-threat-hunters/)