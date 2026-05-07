---
title: Dnssec Failure Causes German Internet Blackout
date: 2026-05-06
categories: [INTERNET]
tags: [DNSSEC,GERMANY,INTERNET,BLACKOUT]
---

## Dnssec Failure Causes German Internet Blackout 🚨

Millions of German websites went dark, and apps stopped working on Tuesday night as Germany's top-level domain (TLD) .de became unreachable. For users, websites like Amazon.de became inaccessible, and key services in the country, including the Deutsche Bahn public transportation app, ceased to function. DNS resolvers around the globe stopped resolving .de domains due to disruption at DENIC eG, the registry managing Germany's TLD. Between around 19:15 and 22:30 UTC on May 5th, DNS queries returned a SERVFAIL error code, indicating that the DNS resolver couldn't provide a valid answer, as reported by Cloudflare Radar data.

DENIC quickly acknowledged the issue, citing "a disruption in its DNS service for .de domains." Cloudflare noted that "apparent DNSSEC problems" were impacting the .de domains. DNSSEC, or DNS Security Extensions, is a security enhancement that adds cryptographic signatures to existing DNS records to ensure they haven't been tampered with. Some network engineers suspect that a botched security key rotation caused the issues. Users on Hacker News reported DNS errors indicating malformed signatures, leading resolvers to refuse to answer the queries. One user mentioned, "Per DENIC's FAQ, the .de Zone Signing Key rotates every 5 weeks via pre-publish, so this smells like a botched rollover."

Leonard M. Schmedding, Co-Founder and Chief AI Officer at Everlast AI, estimated that the disruption affected the entire .de zone, impacting 17.7 million domains, all due to a broken signature record from the Zone Signing Key. Schmedding emphasized on X that "This is the digital infrastructure on which our economy runs," clarifying that there was "No hacker attack. No provider problem. A single cryptographic key at a single authority in Frankfurt and half of Germany is offline. 17.7 million domains. A single point of failure."

The disruption prompted Cloudflare's public DNS service to temporarily disable DNSSEC validation for all .de domains, allowing sites to be reachable while DENIC worked on a fix. Using non-validating DNS resolvers can serve as a workaround when websites are unreachable due to DNSSEC errors.

[Read full article](https://cybernews.com/security/dnssec-failure-causes-german-internet-blackout/)