---
title: Scans for Hikvision Intelligent Security API
date: 2026-07-19
categories: [SECURITY]
tags: [HIKVISION,SECURITY,API,VULNERABILITIES]
---

## Scans for Hikvision Intelligent Security API

Hikvision cameras have a long history of vulnerabilities and are often targeted by internet-wide scans detected by our honeypot network. This weekend, a new type of reconnaissance scans against the newer OPEN Intelligent Security API (ISAPI) provided by Hikvision cameras was noticed. This REST-based API offers access to a wide range of features. Despite using the word **"Intelligent"** in its name, the API is not limited to AI or facial recognition functions; it can fully control the camera settings and manage the camera. The API is intended for integration with various third-party products and is well-documented by Hikvision.

The ISAPI has been around since at least 2018, but scans for `/ISAPI/System/status`, an endpoint that is an obvious choice to profile ISAPI devices, have only now been noticed. Messages can use XML or JSON; most examples seen use XML.

ISAPI requests are authenticated using Basic or Digest authentication. The cameras support HTTPS, but it must first be configured with appropriate keys and certificates. Messages may also be encrypted with AES 128 or 256 in CBC mode. The encryption key is derived from the password, and the IV is exposed in the URL. As a result, the encryption does not provide any additional security if Basic authentication is used and the password is sent in the clear. HTTPS should provide more comprehensive protection.

The URL our sensors noticed this weekend, `/ISAPI/System/status`, returns XML (or JSON) formatted system information. It is likely a simple way to verify whether the device supports ISAPI. The report notes that a 401 or 403 response is expected if the URL exists, and a 404 response if it does not. Additionally, this URL may be useful for brute-forcing a password. So far, honeypots have not captured full requests, but researchers will update if complete requests with authentication data are found. As always, do not expose these cameras to the internet, and do not place them in sensitive areas.

[Read full article](https://isc.sans.edu/forums/diary/Scans%20for%20Hikvision%20Intelligent%20Security%20API/33164/)