---
title: HollowByte DDoS Flaw Bloats OpenSSL Server Memory with 11-Byte Payload
date: 2026-07-17
categories: [SECURITY]
tags: [OPENSSL,DDOS,VULNERABILITY,SECURITY]
---

## HollowByte DDoS Vulnerability 🚨

A vulnerability dubbed **HollowByte** allows unauthenticated attackers to trigger a denial-of-service (DoS) condition on OpenSSL servers with a malicious payload of just **11 bytes**. The OpenSSL team has silently fixed the vulnerability and backported the patch to older releases. Organizations should prioritize switching to a fixed version of the library to ensure secure internet communication.

In an advisory earlier this week, Okta's Red Team described how the HollowByte DoS vulnerability works and its impact in a real-world scenario. The researchers explain that in a TLS handshake, each message has a **4-byte header** for declaring the size of the incoming message. However, vulnerable OpenSSL versions allocate the declared length before receiving the payload and checking its size.

Every TLS handshake message begins with a **4-byte handshake header**, where a three-byte length field discloses the size of the handshake data that should follow. Without validating the payload, the server trusts the packet's claims and allocates the indicated memory. Okta explains, "The worker thread then blocks, waiting indefinitely for data that will never arrive." An unauthenticated attacker can trigger HollowByte by opening a TLS connection and sending an **11-byte malicious input** with a header declaring that a much larger message body will follow. The attacker repeats this process across multiple connections, causing the server to allocate considerable amounts of memory via a relatively small volume of transmitted data.

Okta researchers note that while OpenSSL frees the buffers when a connection drops, the GNU C Library (glibc) handles memory differently and does not immediately return small-to-medium allocations to the operating system; it keeps them for potential reuse. By launching waves of connections with randomized claimed sizes, an attacker prevents the allocator from reusing those freed chunks, causing the server's Resident Set Size (RSS) to climb continuously. Even after the attacker disconnects, the server remains permanently bloated. The only way to fully reclaim the space is by restarting the process.

The open-source OpenSSL library is embedded in popular software projects such as **NGINX** and **Apache** web servers, language runtimes (e.g., Node.js, Python, Ruby, PHP), and databases (MySQL, PostgreSQL). It comes pre-installed on most Linux distributions for TLS encryption and certificate handling. In Okta's tests on NGINX, low-capacity environments can be easily depleted of memory using HollowByte, while higher-spec servers may lose up to **25%** of their memory while the attack bandwidth remains below security alerting thresholds.

The HollowByte DoS issue has been fixed in OpenSSL **4.0.1** and backported to versions **3.6.3**, **3.5.7**, **3.4.6**, and **3.0.21**, which now grow the buffer only when the data arrives, ignoring header claims. Despite being addressed as a "hardening fix" and not a security vulnerability, Okta recommends **upgrading your distribution's OpenSSL packages immediately**.

[Read full article](https://www.bleepingcomputer.com/news/security/hollowbyte-ddos-flaw-bloats-openssl-server-memory-with-11-byte-payload/)