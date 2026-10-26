---
title: Brotli Decoder Flaw Behind Node.js RCE Also Affects Bun, Python and Other Widely Used Software
date: 2026-10-24
categories: [SECURITY]
tags: [BROTLI,NODEJS,PYTHON,VULNERABILITY,SOFTWARE]
---

## Brotli Decoder Flaw Behind Node.js RCE Also Affects Bun, Python and Other Widely Used Software

A memory-corruption flaw in Google's Brotli decoder affects many programs that unpack Brotli-compressed data, including Bun, the Python Brotli and brotlicffi packages, and Envoy proxies configured to decompress Brotli. This vulnerability, tracked as **CVE-2026-111497**, allows crafted compressed data to overwrite memory buffers, potentially leading to crashes, memory leaks, or the execution of attacker-controlled code. 🚨

Imperva researchers have demonstrated that code can run on an unpatched Node.js build, although no real-world attacks have been reported on other software yet. 

The flaw was first disclosed on **October 21**, when Node.js and Google released fixes, with more updates following for affected products. Brotli is a compression format developed by Google, widely used across the web to reduce page sizes and traffic. The bug resides in the C code that unpacks a Brotli stream, affecting any program that reuses this code, from language runtimes to proxies and Python packages. Each program must update its own copy of the decoder. 

### Affected Software
- **Google Brotli (C library)**: Versions 1.0.3 to 1.2.0 (fixed in 1.0.10, 1.1.1, and 1.2.1)
- **Node.js**: Versions 22.x, 24.x, and 26.x before the fix, as well as end-of-life 20.x and older (fixes available in 22.23.4, 24.22.1, and 26.12.1)
- **Bun**: Version 1.4.3 and earlier (fixed in 1.4.4)
- **Envoy**: Versions 1.39.2, 1.38.5, 1.37.7, and 1.36.11 (fixes in 1.40.0, 1.39.3, 1.38.6, 1.37.8, and 1.36.12)
- **Istio**: Versions 1.31.0 to 1.31.1, 1.30.0 to 1.30.5, and 1.29.0 to 1.29.8 (fixes in 1.31.2, 1.30.6, and 1.29.9)
- **Python Brotli**: Version 1.2.0 and earlier (fixed in 1.2.1)
- **Python brotlicffi**: Version 1.2.0.x and earlier (fixed in 1.2.1.0)
- **cdxgen**: Standalone binaries and images, specifically 13.4.0 and 12.8.8 and earlier (fixed in 13.5.0 and 12.8.9)

### Exposure Risks
A program is exposed only if it decodes Brotli data controlled by an external party. For Node.js and Bun, exposure occurs during `fetch()` of a `br` response, via `node:zlib`, or when Express or body-parser processes `br` bodies. A plain Node.js HTTP server does not decode request bodies on its own. Envoy and Istio are affected only if the Brotli decompressor is configured, such as through an Envoy filter. In Python, the risk arises from having the Brotli or brotlicffi package installed. Once either is present, HTTP clients like requests, urllib3, httpx, and aiohttp automatically decode Brotli responses, exposing applications without needing to import Brotli in their code. cdxgen exposure occurs when the standalone binary or image scans untrusted input.

For more details, [Read full article](https://thehackernews.com/2026/10/brotli-decoder-flaw-behind-nodejs-rce.html) 
