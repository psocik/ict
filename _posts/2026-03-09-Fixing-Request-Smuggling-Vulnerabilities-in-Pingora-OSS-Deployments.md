---
title: Fixing Request Smuggling Vulnerabilities in Pingora OSS Deployments
date: 2026-03-09
categories: [SECURITY]
tags: [PINGORA,VULNERABILITIES,SECURITY,CLOUDFLARE]
---

## Fixing Request Smuggling Vulnerabilities in Pingora OSS Deployments

🚨 In December 2025, Cloudflare received reports of HTTP/1.x request smuggling vulnerabilities in the Pingora open source framework when used to build an ingress proxy. The vulnerabilities identified are CVE-2026-2833, CVE-2026-2835, and CVE-2026-2836. These issues were responsibly reported by Rajat Raghav (xclow3n) through our Bug Bounty Program.

🔍 Our investigation found that Cloudflare’s CDN and customer traffic were not affected due to the architecture of our network. However, these vulnerabilities impact standalone Pingora deployments exposed to the Internet, potentially allowing an attacker to:
- Bypass Pingora proxy-layer security controls
- Desynchronize HTTP request/responses with backends for cross-user hijacking attacks (session or credential theft)
- Poison Pingora proxy-layer caches retrieving content from shared backends

🛠️ We have released Pingora 0.8.0 with fixes and hardening. While Cloudflare customers were not affected, we strongly recommend users of the Pingora framework to upgrade as soon as possible.

📜 The reports described various HTTP/1 attack payloads that could cause desynchronization attacks. Such requests could lead to the proxy and backend disagreeing about where the request body ends, allowing a second request to be “smuggled” past proxy-layer checks.

🔧 One reported vulnerability involved a premature upgrade without a 101 handshake. The first report showed that a request with an `Upgrade` header value would cause Pingora to pass through subsequent bytes on the HTTP connection immediately, before the backend had accepted an upgrade (by returning `101 Switching Protocols`). This could allow an attacker to pipeline a second HTTP request after the upgrade request on the same connection.

⚠️ We’ve since patched Pingora to switch the interpretation of subsequent bytes only once the upstream responds with `101 Switching Protocols`. We verified that Cloudflare was not affected for two reasons:
1. The ingress CDN proxies do not exhibit this improper behavior.
2. The clients to our internal Pingora services do not attempt to pipeline.

For more details, please read the complete article: [Read full article](https://blog.cloudflare.com/pingora-oss-smuggling-vulnerabilities/)