---
title: Simple Scans for Cloud Metadata Service
date: 2026-08-19
categories: [SECURITY]
tags: [CLOUD,METADATA,SECURITY,VULNERABILITY,SSRF]
---

## Simple Scans for Cloud Metadata Service

Cloud providers typically expose a REST API at **169.254.169.254** that allows code running on virtual machines to retrieve machine-specific data. Some of the data is more or less harmless, such as the region the machine is running in or its MAC and IP addresses. However, the service may also be used to retrieve credentials for IAM roles and service account tokens. The address **169.254.169.254** is part of the link local address prefix **169.254/16** [RFC3927]. These addresses are specifically not routable, unlike RFC 1918 addresses, which may be routed locally. 

> "The host MUST NOT send a packet with an IPv4 Link-Local destination address to any router for forwarding."

This unique property of link-local addresses makes them ideal for addresses used multiple times, and that must never be routed. 🚀 

An attacker will not be able to reach out to this address remotely. But there is a "trick": the virtual machine itself can reach the metadata service, and if an attacker uses server-side request forgery (SSRF) to trick the server into sending the request, the address may be reached. The attacker could now use this SSRF vulnerability to retrieve secrets. Probably the best-known breach assisted by the metadata service was **Capital One**, which led to a huge data leak and later to the prosecution of the attacker. Since then, we have seen attempts to exploit SSRF vulnerabilities in order to access the metadata service. 

What has been noticed recently is a widespread scan that appears to be not targeted at a particular vulnerability. This scan involves requests such as:

```
GET /?url=https://169.254.169.254/latest/meta-data/iam/security-credentials/ HTTP/1.1
Host: [redacted]
User-Agent: Go-http-client/1.1
Accept-Encoding: gzip
```

This scan does not appear to target a specific vulnerability; it is a more generic attempt to find "some" vulnerability, and it is not clear which one. 

As far as securing the metadata service goes, Amazon used version 2 of the service following the Capital One breach. A simple "GET" request is no longer sufficient, making SSRF access highly unlikely. For IPv6, the service uses **fd20:ce::254**, which is a unique local address, more like an RFC 1918 address instead of an IPv6 link-local **fe80::** address. 

[Read full article](https://isc.sans.edu/forums/diary/Simple%20Scans%20for%20Cloud%20Metadata%20Service/33260/)